---
title: Восстановление базы данных (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoredb.general.f1
ms.assetid: 160cf58c-b06a-475f-9a69-2b051e5767ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a497e6a6e4584aa064783eba2076b7e50b36e8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666677"
---
# <a name="restore-database-general-page"></a><span data-ttu-id="7a76e-102">Восстановление базы данных (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="7a76e-102">Restore Database (General Page)</span></span>
  <span data-ttu-id="7a76e-103">Страница **Общие** позволяет задать данные об исходной и целевой базах данных для операции восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-103">Use the **General** page to specify information about the target and source databases for a database-restore operation.</span></span>  
  
 <span data-ttu-id="7a76e-104">**Восстановление резервной копии базы данных с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="7a76e-104">**To use SQL Server Management Studio to restore a database backup**</span></span>  
  
-   [<span data-ttu-id="7a76e-105">Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7a76e-105">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="7a76e-106">Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a76e-106">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
> [!NOTE]  
>  <span data-ttu-id="7a76e-107">При указании задачи восстановления с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] можно создать соответствующий [!INCLUDE[tsql](../../includes/tsql-md.md)] скрипт [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , нажав кнопку **Скрипт** и выбрав место назначения для скрипта.</span><span class="sxs-lookup"><span data-stu-id="7a76e-107">When you specify a restore task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) script by clicking **Script** and then selecting a destination for the script.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="7a76e-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="7a76e-108">Permissions</span></span>  
 <span data-ttu-id="7a76e-109">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="7a76e-109">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="7a76e-110">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="7a76e-110">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database.</span></span>  
  
 <span data-ttu-id="7a76e-111">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="7a76e-111">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="7a76e-112">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="7a76e-112">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
 <span data-ttu-id="7a76e-113">Восстановление из зашифрованной копии требует разрешений `VIEW DEFINITION` на сертификат или асимметричный ключ, используемые для создания зашифрованной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7a76e-113">Restoring from an encrypted backup requires `VIEW DEFINITION` permissions to the certificate or asymmetric key used to encrypt during backup.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a76e-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="7a76e-114">Options</span></span>  
  
### <a name="source"></a><span data-ttu-id="7a76e-115">Источник</span><span class="sxs-lookup"><span data-stu-id="7a76e-115">Source</span></span>  
 <span data-ttu-id="7a76e-116">Параметры панели **Восстановить из**определяют, где расположены наборы архивации для базы данных и какие наборы архивации требуется восстановить.</span><span class="sxs-lookup"><span data-stu-id="7a76e-116">The options of the **Restore from**panel identify the location of the backup sets for the database and which backup sets you want to restore.</span></span>  
  
|<span data-ttu-id="7a76e-117">Термин</span><span class="sxs-lookup"><span data-stu-id="7a76e-117">Term</span></span>|<span data-ttu-id="7a76e-118">Определение</span><span class="sxs-lookup"><span data-stu-id="7a76e-118">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="7a76e-119">**База данных**</span><span class="sxs-lookup"><span data-stu-id="7a76e-119">**Database**</span></span>|<span data-ttu-id="7a76e-120">Выберите из раскрывающегося списка базу данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-120">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="7a76e-121">Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .</span><span class="sxs-lookup"><span data-stu-id="7a76e-121">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>|  
|<span data-ttu-id="7a76e-122">**Устройство**</span><span class="sxs-lookup"><span data-stu-id="7a76e-122">**Device**</span></span>|<span data-ttu-id="7a76e-123">Выберите логические или физические устройства резервного копирования (ленты, URL-адрес или файлы), которые содержат резервные копии, необходимые для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-123">Select the logical or physical backup devices (tapes, URL or files) that contain the backup or backups you want to restore.</span></span> <span data-ttu-id="7a76e-124">Это необходимо, если при создании резервной копии базы данных использовался другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a76e-124">This is required if the database backup was taken on a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="7a76e-125">Чтобы выбрать одно или несколько логических или физических устройств резервного копирования, нажмите кнопку обзора, которая открывает диалоговое окно **Выбор устройства резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="7a76e-125">To select one or more logical or physical backup devices, click the browse button which opens the **Select backup devices** dialog box.</span></span> <span data-ttu-id="7a76e-126">В этом диалоговом окне можно выбрать до 64 устройств, принадлежащих к одному набору носителей.</span><span class="sxs-lookup"><span data-stu-id="7a76e-126">There, you can select up to 64 devices that belong to a single media set.</span></span> <span data-ttu-id="7a76e-127">Ленточные устройства должны быть физически подключены к компьютеру, на котором работает экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a76e-127">Tape devices must be physically connected to the computer that is running the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7a76e-128">Файл резервной копии может находиться на локальном или удаленном дисковом устройстве.</span><span class="sxs-lookup"><span data-stu-id="7a76e-128">A backup file can be on a local or remove disk device.</span></span> <span data-ttu-id="7a76e-129">Дополнительные сведения см. в разделе [Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a76e-129">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span> <span data-ttu-id="7a76e-130">Кроме того, можно выбрать **URL-адрес** в качестве типа устройства для файлов резервных копий, размещаемых в хранилище Azure.</span><span class="sxs-lookup"><span data-stu-id="7a76e-130">You can also select **URL** as the  device type for backup files stored in Azure storage.</span></span><br /><br /> <span data-ttu-id="7a76e-131">После выхода из диалогового окна **Выбор устройства резервного копирования** выбранное устройство появляется в виде значения, доступного только для чтения, в списке **Устройство** .</span><span class="sxs-lookup"><span data-stu-id="7a76e-131">When you exit the **Select backup devices** dialog box, the selected device will appear as read-only values in the **Device** list.</span></span>|  
|<span data-ttu-id="7a76e-132">**База данных**</span><span class="sxs-lookup"><span data-stu-id="7a76e-132">**Database**</span></span>|<span data-ttu-id="7a76e-133">Выберите из раскрывающегося списка имя базы данных, из которой нужно восстановить резервные копии.</span><span class="sxs-lookup"><span data-stu-id="7a76e-133">Select the database name from which the backups should be restored from the dropdown list.</span></span><br /><br /> <span data-ttu-id="7a76e-134">Примечание. Данный список доступен, только если выбран параметр **Устройство** .</span><span class="sxs-lookup"><span data-stu-id="7a76e-134">Note: This list is only available when **Device** is selected.</span></span> <span data-ttu-id="7a76e-135">Будут выбраны только те базы данных, резервные копии которых доступны на выбранных устройствах.</span><span class="sxs-lookup"><span data-stu-id="7a76e-135">Only databases that have backups on the selected devices will be available.</span></span>|  
  
### <a name="destination"></a><span data-ttu-id="7a76e-136">Назначение</span><span class="sxs-lookup"><span data-stu-id="7a76e-136">Destination</span></span>  
 <span data-ttu-id="7a76e-137">Параметры панели **Восстановить в** определяют базу данных и точку восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-137">The options of the **Restore to** panel identify the database and restore point.</span></span>  
  
|<span data-ttu-id="7a76e-138">Термин</span><span class="sxs-lookup"><span data-stu-id="7a76e-138">Term</span></span>|<span data-ttu-id="7a76e-139">Определение</span><span class="sxs-lookup"><span data-stu-id="7a76e-139">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="7a76e-140">**База данных**</span><span class="sxs-lookup"><span data-stu-id="7a76e-140">**Database**</span></span>|<span data-ttu-id="7a76e-141">Введите в список базу данных, предназначенную для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-141">Enter the database to restore in the list.</span></span> <span data-ttu-id="7a76e-142">Можно ввести новую базу данных или выбрать уже существующую из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7a76e-142">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="7a76e-143">Список включает все базы данных на сервере кроме системных баз данных **master** и **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7a76e-143">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span><br /><br /> <span data-ttu-id="7a76e-144">Примечание. Для восстановления резервной копии, защищенной паролем, необходимо использовать инструкцию [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="7a76e-144">Note: To restore a password-protected backup, you must use the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement.</span></span>|  
|<span data-ttu-id="7a76e-145">**Восстановить в**</span><span class="sxs-lookup"><span data-stu-id="7a76e-145">**Restore to**</span></span>|<span data-ttu-id="7a76e-146">В поле **Восстановить до** по умолчанию задан параметр «До последней созданной резервной копии».</span><span class="sxs-lookup"><span data-stu-id="7a76e-146">The **Restore to** box will be set "To the last backup taken" by default.</span></span> <span data-ttu-id="7a76e-147">Можно также щелкнуть **Временную шкалу** , чтобы вывести диалоговое окно **Временная шкала резервного копирования** , содержащее журнал резервного копирования баз данных в виде временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="7a76e-147">You can also click **Timeline** to show the **Backup Timeline** dialog box, which displays the database backup history in the form of a timeline.</span></span> <span data-ttu-id="7a76e-148">Щелкните **временная шкала** , чтобы указать конкретную, `datetime` для которой необходимо восстановить базу данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-148">Click **Timeline** to designate a specific `datetime` to which you want to restore the database.</span></span> <span data-ttu-id="7a76e-149">База данных будет восстановлена до состояния, в котором она находилась в указанный момент времени.</span><span class="sxs-lookup"><span data-stu-id="7a76e-149">The database will then be restored to the state it was in at this specified point in time.</span></span> <span data-ttu-id="7a76e-150">См. раздел [Backup Timeline](backup-timeline.md).</span><span class="sxs-lookup"><span data-stu-id="7a76e-150">See [Backup Timeline](backup-timeline.md).</span></span>|  
  
### <a name="restore-plan"></a><span data-ttu-id="7a76e-151">План восстановления</span><span class="sxs-lookup"><span data-stu-id="7a76e-151">Restore Plan</span></span>  
  
|<span data-ttu-id="7a76e-152">Термин</span><span class="sxs-lookup"><span data-stu-id="7a76e-152">Term</span></span>|<span data-ttu-id="7a76e-153">Определение</span><span class="sxs-lookup"><span data-stu-id="7a76e-153">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="7a76e-154">**Резервные наборы данных, которые необходимо восстановить**</span><span class="sxs-lookup"><span data-stu-id="7a76e-154">**Backup sets to restore**</span></span>|<span data-ttu-id="7a76e-155">Отображает резервный набор данных, доступный для указанного места.</span><span class="sxs-lookup"><span data-stu-id="7a76e-155">Displays the backup sets available for the specified location.</span></span> <span data-ttu-id="7a76e-156">Каждый резервный набор данных (результат одной операции резервного копирования) распределяется по всем устройствам в наборе носителей.</span><span class="sxs-lookup"><span data-stu-id="7a76e-156">Each backup set, the result of a single backup operation, is distributed across all of the devices in the media set.</span></span> <span data-ttu-id="7a76e-157">По умолчанию предполагается наличие плана восстановления, направленного на достижение целей операции восстановления и основанного на выборе необходимых резервных наборов данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-157">By default, a recovery plan is suggested to achieve the goal of the restore operation that is based on the selection of the required backup sets.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="7a76e-158">использует журнал резервного копирования в базе данных **msdb** , чтобы определить резервные наборы данных, необходимые для восстановления базы данных, и создает план восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-158">uses the backup history in **msdb** to identify which backups are required to restore a database, and creates a restore plan.</span></span> <span data-ttu-id="7a76e-159">Например, для восстановления базы данных план восстановления выбирает самую последнюю полную резервную копию базы данных и самую последнюю разностную резервную копию базы данных при ее наличии.</span><span class="sxs-lookup"><span data-stu-id="7a76e-159">For example, for a database restore, the restore plan selects the most recent full database backup followed by the most recent subsequent differential database backup, if any.</span></span> <span data-ttu-id="7a76e-160">Согласно модели полного восстановления план восстановления выбирает затем все последующие резервные копии журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="7a76e-160">Under the full recovery model, the restore plan then selects all subsequent log backups.</span></span><br /><br /> <span data-ttu-id="7a76e-161">Чтобы переопределить предлагаемый план восстановления, можно изменить следующие параметры в сетке.</span><span class="sxs-lookup"><span data-stu-id="7a76e-161">To override the suggested recovery plan, you can change the following selections in the grid.</span></span> <span data-ttu-id="7a76e-162">Если выбор каких-то резервных копий отменяется, то автоматически отменяется и выбор зависящих от них резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7a76e-162">Any backups that depend on a deselected backup are deselected automatically.</span></span><br /><br /> <span data-ttu-id="7a76e-163">**Восстановление**.</span><span class="sxs-lookup"><span data-stu-id="7a76e-163">**Restore**:</span></span><br />                          <span data-ttu-id="7a76e-164">Установленные флажки обозначают резервные наборы данных, отмеченные для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-164">The selected check boxes indicate the backup sets to be restored.</span></span><br /><span data-ttu-id="7a76e-165">**Имя**. имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-165">**Name**: The name of the backup set.</span></span><br /><span data-ttu-id="7a76e-166">**Компонент**: компонент, резервная копия которого: **база данных**, **файл**или **\<blank>** (для журналов транзакций).</span><span class="sxs-lookup"><span data-stu-id="7a76e-166">**Component**: The backed-up component: **Database**, **File**, or **\<blank>** (for transaction logs).</span></span><br /><span data-ttu-id="7a76e-167">**Тип**. Тип выполняемого резервного копирования: **Полное**, **Разностное**или **Журнал транзакций**.</span><span class="sxs-lookup"><span data-stu-id="7a76e-167">**Type**: The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span><br /><span data-ttu-id="7a76e-168">**Сервер**: Имя экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7a76e-168">**Server**: The name of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance that performed the backup operation.</span></span><br /><span data-ttu-id="7a76e-169">**База данных**: имя базы данных, участвующей в операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7a76e-169">**Database**: The name of the database involved in the backup operation.</span></span><br /><span data-ttu-id="7a76e-170">**Положение**: Расположение резервного набора данных в томе.</span><span class="sxs-lookup"><span data-stu-id="7a76e-170">**Position**: The position of the backup set in the volume.</span></span><br /><span data-ttu-id="7a76e-171">**Первый номер LSN**: Регистрационный номер транзакции в журнале первой в резервном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-171">**First LSN**: The log sequence number of the first transaction in the backup set.</span></span> <span data-ttu-id="7a76e-172">Пустой для резервных копий файлов.</span><span class="sxs-lookup"><span data-stu-id="7a76e-172">Blank for file backups.</span></span><br /><span data-ttu-id="7a76e-173">**Последний номер LSN**: Регистрационный номер транзакции в журнале, последний в резервном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-173">**Last LSN**: The log sequence number of the last transaction in the backup set.</span></span> <span data-ttu-id="7a76e-174">Пустой для резервных копий файлов.</span><span class="sxs-lookup"><span data-stu-id="7a76e-174">Blank for file backups.</span></span><br /><span data-ttu-id="7a76e-175">Номер **LSN контрольной точки**: Регистрационный номер транзакции в журнале (LSN) для последней контрольной точки на момент создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7a76e-175">**Checkpoint LSN**: The log sequence number (LSN) of the most recent checkpoint at the time the backup was created.</span></span><br /><span data-ttu-id="7a76e-176">**Полный номер LSN**. Регистрационный номер последней полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-176">**Full LSN**: The log sequence number of the most recent full database backup.</span></span><br /><span data-ttu-id="7a76e-177">**Дата начала**: Дата и время начала операции резервного копирования, представленные в региональных настройках клиента.</span><span class="sxs-lookup"><span data-stu-id="7a76e-177">**Start Date**: The date and time when the backup operation began, presented in the regional setting of the client.</span></span><br /><span data-ttu-id="7a76e-178">**Дата окончания**: Дата и время завершения операции резервного копирования, представленные в региональных настройках клиента.</span><span class="sxs-lookup"><span data-stu-id="7a76e-178">**Finish Date**: The date and time when the backup operation finished, presented in the regional setting of the client.</span></span><br /><span data-ttu-id="7a76e-179">**Размер**: Размер резервного набора данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="7a76e-179">**Size**: The size of the backup set in bytes.</span></span><br /><span data-ttu-id="7a76e-180">**Имя пользователя**: имя пользователя, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7a76e-180">**User Name**: The name of the user who performed the backup operation.</span></span><br /><br /> <span data-ttu-id="7a76e-181">**Срок действия**. Дата и время истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="7a76e-181">**Expiration**: The date and time the backup set expires.</span></span><br /><br /> <span data-ttu-id="7a76e-182">Установка этих флажков возможна, только если задан параметр **Выбор вручную** .</span><span class="sxs-lookup"><span data-stu-id="7a76e-182">The checkboxes are only enabled when the **Manual Selection** box is checked.</span></span> <span data-ttu-id="7a76e-183">Позволяет выбрать, какие наборы резервного копирования необходимо восстановить.</span><span class="sxs-lookup"><span data-stu-id="7a76e-183">This allows you to select which backup-sets are to be restored.</span></span><br /><br /> <span data-ttu-id="7a76e-184">Если задан параметр **Выбор вручную** , точность плана восстановления проверяется каждый раз при его изменении.</span><span class="sxs-lookup"><span data-stu-id="7a76e-184">When the **Manual Selection** box is checked, the accuracy of the Restore Plan is checked each time it is modified.</span></span> <span data-ttu-id="7a76e-185">Если последовательность резервных копий является неверной, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7a76e-185">If the sequence of backups is incorrect, an error message will appear.</span></span>|  
|<span data-ttu-id="7a76e-186">**Проверить носитель резервной копии**</span><span class="sxs-lookup"><span data-stu-id="7a76e-186">**Verify Backup Media**</span></span>|<span data-ttu-id="7a76e-187">Инструкция RESTORE VERIFY_ONLY вызывается для выбранных наборов резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7a76e-187">Calls a RESTORE VERIFY_ONLY statement on the selected backup-sets.</span></span><br /><br /> <span data-ttu-id="7a76e-188">Примечание. Это длительная операция, и ее выполнение или отмену можно выполнить с помощью монитора хода выполнения на платформе диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="7a76e-188">Note: This is a long-running operation, and its progress can be tracked and cancelled by using the Progress Monitor on the Dialog Framework.</span></span><br /><br /> <span data-ttu-id="7a76e-189">Эта кнопка позволяет проверить целостность файлов резервной копии до их восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-189">This button allows you to check the integrity of the selected backup files prior to restoring them.</span></span><br /><br /> <span data-ttu-id="7a76e-190">При проверке целостности резервных наборов данных в статусе выполнения в нижнем левом углу диалогового окна будет указано «Проверка», а не «Выполнение».</span><span class="sxs-lookup"><span data-stu-id="7a76e-190">When checking the integrity of backup sets, the progress status at the bottom left of the dialog box will read "Verifying" rather than "Executing."</span></span>|  
  
## <a name="compatibility-support"></a><span data-ttu-id="7a76e-191">Поддержка совместимости</span><span class="sxs-lookup"><span data-stu-id="7a76e-191">Compatibility Support</span></span>  
 <span data-ttu-id="7a76e-192">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]можно восстановить пользовательскую базу данных из резервной копии базы данных, созданной с помощью [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="7a76e-192">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can restore a user database from a database backup that was created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version.</span></span> <span data-ttu-id="7a76e-193">Однако восстановление резервных копий баз данных **master**, **model** и **msdb** , созданных в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] через [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]невозможно.</span><span class="sxs-lookup"><span data-stu-id="7a76e-193">However, backups of **master**, **model** and **msdb** that were created by using [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] through [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] cannot be restored by [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7a76e-194">Кроме того, резервные копии, созданные в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , невозможно восстановить в более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a76e-194">Also, backups created in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] cannot be restored by any earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="7a76e-195">используется путь по умолчанию, отличный от пути, использованного в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="7a76e-195">uses a different default path than earlier versions.</span></span> <span data-ttu-id="7a76e-196">Поэтому, чтобы восстановить из резервной копии базу данных, созданную в расположении по умолчанию для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]предыдущих версий, необходимо использовать параметр MOVE.</span><span class="sxs-lookup"><span data-stu-id="7a76e-196">Therefore, to restore a database that was created in the default location of an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must use the MOVE option.</span></span>  
  
 <span data-ttu-id="7a76e-197">Если восстановить базу данных предыдущей версии до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], то эта база данных автоматически обновится.</span><span class="sxs-lookup"><span data-stu-id="7a76e-197">After you restore an earlier version database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database is automatically upgraded.</span></span> <span data-ttu-id="7a76e-198">Как правило, база данных сразу становится доступной.</span><span class="sxs-lookup"><span data-stu-id="7a76e-198">Typically, the database becomes available immediately.</span></span> <span data-ttu-id="7a76e-199">Однако если база данных [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] содержит полнотекстовые индексы, то в процессе обновления будет произведен их импорт, сброс или перестроение, в зависимости от установленного значения свойства сервера **Режим обновления полнотекстового каталога** .</span><span class="sxs-lookup"><span data-stu-id="7a76e-199">However, if a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the **Full-Text Upgrade Option** server property.</span></span> <span data-ttu-id="7a76e-200">Если при обновлении выбран режим **Импортировать** или **Перестроить**, то полнотекстовые индексы во время обновления будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="7a76e-200">If the upgrade option is set to **Import** or **Rebuild**, the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="7a76e-201">В зависимости от объема индексируемых данных процесс импорта может занять несколько часов, а перестроение — в несколько (до десяти) раз больше.</span><span class="sxs-lookup"><span data-stu-id="7a76e-201">Depending upon the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="7a76e-202">Обратите внимание, что если при обновлении выбран режим **Импортировать**, а полнотекстовый каталог недоступен, то связанные с ним полнотекстовые индексы будут перестроены.</span><span class="sxs-lookup"><span data-stu-id="7a76e-202">Note also that when the upgrade option is set to **Import**, if a full-text catalog is not available, the associated full-text indexes are rebuilt.</span></span>  
  
## <a name="restoring-from-an-encrypted-backup"></a><span data-ttu-id="7a76e-203">Восстановление из зашифрованной резервной копии</span><span class="sxs-lookup"><span data-stu-id="7a76e-203">Restoring from an Encrypted Backup</span></span>  
 <span data-ttu-id="7a76e-204">Для восстановления требуется, чтобы сертификат или асимметричный ключ, который использовался при создании резервной копии, был доступен на экземпляре, куда выполняется восстановление.</span><span class="sxs-lookup"><span data-stu-id="7a76e-204">Restore requires that the certificate or asymmetric key that was originally used to create the backup is available on the instance you are restoring to.</span></span> <span data-ttu-id="7a76e-205">Учетная запись, выполняющая восстановление, должна иметь разрешения `VIEW DEFINITIONS` на сертификат или асимметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="7a76e-205">The account performing the restore should have `VIEW DEFINITIONS` on the certificate or asymmetric key.</span></span> <span data-ttu-id="7a76e-206">Сертификаты, используемые для шифрования резервных копий, не должны обновляться.</span><span class="sxs-lookup"><span data-stu-id="7a76e-206">Certificates used to encrypt backup should not be renewed or updated.</span></span>  
  
## <a name="restoring-from-azure-storage"></a><span data-ttu-id="7a76e-207">Восстановление из хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="7a76e-207">Restoring from Azure Storage</span></span>  
 <span data-ttu-id="7a76e-208">При восстановлении резервной копии, хранящейся в службе хранилища Azure, в пользовательском интерфейсе восстановления имеется новый параметр устройство резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7a76e-208">When restoring a backup stored in Azure storage, the Restore UI has a new backup device option.</span></span> <span data-ttu-id="7a76e-209">**URL-адрес** в диалоговом окне **Выбор устройства резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="7a76e-209">**URL** on the **Select backup devices** dialog.</span></span> <span data-ttu-id="7a76e-210">При нажатии кнопки " **Добавить**" откроется диалоговое окно " **Подключение к Azure** ", в котором можно указать учетные данные SQL для проверки подлинности в учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="7a76e-210">When you click **Add**, this takes you to the **Connect to Azure** dialog that allows you to specify the SQL Credential information to authenticate to the storage account.</span></span>  <span data-ttu-id="7a76e-211">После подключения к учетной записи хранения файлы резервной копии отображаются в диалоговом окне **расположение файла резервной копии в Azure** , где можно выбрать файл, который будет использоваться для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a76e-211">Once connected to the storage account, the backup files are displayed in the **Locate a Backup file in Azure** dialog where you can select the file to use for the restore.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a76e-212">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a76e-212">See Also</span></span>  
 <span data-ttu-id="7a76e-213">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a76e-213">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="7a76e-214">[Восстановление резервной копии с устройства (SQL Server)](restore-a-backup-from-a-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a76e-214">[Restore a Backup from a Device &#40;SQL Server&#41;](restore-a-backup-from-a-device-sql-server.md) </span></span>  
 <span data-ttu-id="7a76e-215">[Восстановление базы данных до помеченной транзакции (среда SQL Server Management Studio)](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7a76e-215">[Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="7a76e-216">[Восстановление резервной копии журнала транзакций (SQL Server)](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a76e-216">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 <span data-ttu-id="7a76e-217">[Просмотр содержимого ленты или файла резервной копии (SQL Server)](view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a76e-217">[View the Contents of a Backup Tape or File &#40;SQL Server&#41;](view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span></span>  
 <span data-ttu-id="7a76e-218">[Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a76e-218">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="7a76e-219">[Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a76e-219">[Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md) </span></span>  
 <span data-ttu-id="7a76e-220">[Аргументы инструкции RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a76e-220">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 [<span data-ttu-id="7a76e-221">Применение резервных копий журналов транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a76e-221">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](transaction-log-backups-sql-server.md)  
  
  