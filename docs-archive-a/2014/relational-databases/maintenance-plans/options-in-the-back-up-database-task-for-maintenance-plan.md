---
title: Задача "Резервное копирование базы данных" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.backup.f1
- sql12.swb.maint.maintplanproperties.logbackup.f1
helpviewer_keywords:
- Back Up Database Task dialog box
ms.assetid: ed1ef012-fa14-4ba5-bafe-d1527ba065b3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 952730f09deeede360dff5e2bd83f8cdc8a20a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658236"
---
# <a name="back-up-database-task-maintenance-plan"></a><span data-ttu-id="65f7a-102">Задача «Резервное копирование базы данных» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="65f7a-102">Back Up Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="65f7a-103">Используйте диалоговое окно **Задача «Резервное копирование базы данных»** , чтобы добавить задачу резервного копирования в план обслуживания.</span><span class="sxs-lookup"><span data-stu-id="65f7a-103">Use the **Back Up Database Task** dialog to add a backup task to the maintenance plan.</span></span> <span data-ttu-id="65f7a-104">Резервное копирование баз данных важно на случай системного или аппаратного сбоя (или ошибок пользователя), которые приводят к повреждению базы данных, в таком случае база данных восстанавливается из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="65f7a-104">Backing up the database is important in case of system or hardware failure (or user errors) that cause the database to be damaged in some way, thus requiring a backed-up copy to be restored.</span></span> <span data-ttu-id="65f7a-105">Эта задача позволяет выполнять полное и разностное резервное копирование, резервное копирование файлов, файловых групп и журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="65f7a-105">This task allows you to perform full, differential, files and filegroups, and transaction log backups.</span></span>  
  
 <span data-ttu-id="65f7a-106">**Создание задачи резервного копирования базы данных**</span><span class="sxs-lookup"><span data-stu-id="65f7a-106">**To create a backup database task**</span></span>  
  
-   [<span data-ttu-id="65f7a-107">Создание плана обслуживания</span><span class="sxs-lookup"><span data-stu-id="65f7a-107">Create a Maintenance Plan</span></span>](create-a-maintenance-plan.md)  
  
## <a name="options"></a><span data-ttu-id="65f7a-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="65f7a-108">Options</span></span>  
 <span data-ttu-id="65f7a-109">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="65f7a-109">**Connection**</span></span>  
 <span data-ttu-id="65f7a-110">Выберите соединение с сервером, которое будет использоваться для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="65f7a-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="65f7a-111">**Создать**</span><span class="sxs-lookup"><span data-stu-id="65f7a-111">**New**</span></span>  
 <span data-ttu-id="65f7a-112">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="65f7a-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="65f7a-113">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="65f7a-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="65f7a-114">**Базы данных**</span><span class="sxs-lookup"><span data-stu-id="65f7a-114">**Databases**</span></span>  
 <span data-ttu-id="65f7a-115">Укажите базы данных, для которых должна выполняться эта задача.</span><span class="sxs-lookup"><span data-stu-id="65f7a-115">Specify the databases affected by this task.</span></span> <span data-ttu-id="65f7a-116">При выборе этот раскрывающийся список содержит следующие пункты: **Все базы данных**, **Все системные базы данных**, **Все пользовательские базы данных**, **Определенные базы данных**.</span><span class="sxs-lookup"><span data-stu-id="65f7a-116">When selected, the drop down list provides the following options: **All databases**, **All system databases**, **All user databases**, **These specific databases**.</span></span>  
  
 <span data-ttu-id="65f7a-117">**Все базы данных**</span><span class="sxs-lookup"><span data-stu-id="65f7a-117">**All databases**</span></span>  
 <span data-ttu-id="65f7a-118">Создается план обслуживания, по которому задачи обслуживания выполняются для всех баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65f7a-118">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="65f7a-119">**Все системные базы данных (master, msdb, model)**</span><span class="sxs-lookup"><span data-stu-id="65f7a-119">**All system databases (master, msdb, model)**</span></span>  
 <span data-ttu-id="65f7a-120">Создается план обслуживания, по которому задачи обслуживания выполняются для всех системных баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65f7a-120">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span> <span data-ttu-id="65f7a-121">Для баз данных, созданных пользователями, задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="65f7a-121">No maintenance tasks are run against user-created databases.</span></span>  
  
 <span data-ttu-id="65f7a-122">**Все пользовательские базы данных (кроме master, model, msdb, tempdb)**</span><span class="sxs-lookup"><span data-stu-id="65f7a-122">**All user databases (excluding master, model, msdb, tempdb)**</span></span>  
 <span data-ttu-id="65f7a-123">Создается план обслуживания, по которому задачи обслуживания выполняются для всех баз данных, созданных пользователем.</span><span class="sxs-lookup"><span data-stu-id="65f7a-123">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="65f7a-124">Для системных баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задачи обслуживания выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="65f7a-124">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
 <span data-ttu-id="65f7a-125">**Следующие базы данных**</span><span class="sxs-lookup"><span data-stu-id="65f7a-125">**These databases**</span></span>  
 <span data-ttu-id="65f7a-126">Создается план обслуживания, по которому задачи обслуживания должны выполняться только для указанных баз данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-126">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="65f7a-127">Если выбран этот параметр, необходимо выбрать в списке хотя бы одну базу данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-127">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="65f7a-128">**Тип резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="65f7a-128">**Backup type**</span></span>  
 <span data-ttu-id="65f7a-129">Отображает тип резервной копии, которая будет создана.</span><span class="sxs-lookup"><span data-stu-id="65f7a-129">Shows the type of backup to be performed.</span></span>  
  
 <span data-ttu-id="65f7a-130">**Компонент резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="65f7a-130">**Backup component**</span></span>  
 <span data-ttu-id="65f7a-131">Выберите **База данных** для создания резервной копии всей базы данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-131">Select **Database** to back up the entire database.</span></span> <span data-ttu-id="65f7a-132">Выберите **Файл и файловые группы** для создания резервной копии части базы данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-132">Select **File and filegroups** to back up only a portion of the database.</span></span> <span data-ttu-id="65f7a-133">При выборе этого значения укажите имя файла или файловой группы.</span><span class="sxs-lookup"><span data-stu-id="65f7a-133">If selected, provide the file or filegroup name.</span></span> <span data-ttu-id="65f7a-134">Если в окне **Базы данных** выбрано несколько баз данных, то в области **Компонент резервного копирования** выберите только **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="65f7a-134">When multiple databases are selected in the **Databases** box, only specify **Databases** for the **Backup components**.</span></span> <span data-ttu-id="65f7a-135">Для резервного копирования файлов или файловых групп создайте задачу для каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-135">To perform file or filegroup backups, create a task for each database.</span></span>  
  
 <span data-ttu-id="65f7a-136">**Срок действия резервного набора данных истекает**</span><span class="sxs-lookup"><span data-stu-id="65f7a-136">**Backup set will expire**</span></span>  
 <span data-ttu-id="65f7a-137">Укажите, когда резервный набор данных можно переписать другим резервным набором данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-137">Specify when the backup set can be overwritten by another backup set.</span></span>  
  
 <span data-ttu-id="65f7a-138">**Создать резервную копию на**</span><span class="sxs-lookup"><span data-stu-id="65f7a-138">**Back up to**</span></span>  
 <span data-ttu-id="65f7a-139">Создает резервную копию базы данных в файле или на ленте.</span><span class="sxs-lookup"><span data-stu-id="65f7a-139">Back up the database to a file or to tape.</span></span> <span data-ttu-id="65f7a-140">Доступны только ленточные устройства, подключенные к компьютеру, на котором находится база данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-140">Only tape devices attached to the computer containing the database are available.</span></span>  
  
 <span data-ttu-id="65f7a-141">**Создать резервную копию базы данных в одном или нескольких файлах**</span><span class="sxs-lookup"><span data-stu-id="65f7a-141">**Back up databases across one or more files**</span></span>  
 <span data-ttu-id="65f7a-142">Нажмите кнопку **Добавить** для открытия диалогового окна **Выбор места расположения резервной копии** и укажите одно или несколько мест на диске или ленточных устройств.</span><span class="sxs-lookup"><span data-stu-id="65f7a-142">Click **Add** to open the **Select Backup Destination** dialog box, and provide one or more a disk location, or tape device.</span></span>  
  
 <span data-ttu-id="65f7a-143">**Если файлы резервной копии существуют**</span><span class="sxs-lookup"><span data-stu-id="65f7a-143">**If backup files exist**</span></span>  
 <span data-ttu-id="65f7a-144">Выберите **Присоединить** , чтобы добавить эту резервную копию в конец файла.</span><span class="sxs-lookup"><span data-stu-id="65f7a-144">Select **Append** to add this backup to the end of the file.</span></span> <span data-ttu-id="65f7a-145">Выберите **Перезаписать**, чтобы удалить любые устаревшие резервные копии в файле и заменить их создаваемой новой резервной копией.</span><span class="sxs-lookup"><span data-stu-id="65f7a-145">Select **Overwrite**, to remove any old backup in the file and replace them with this new backup.</span></span>  
  
 <span data-ttu-id="65f7a-146">**Создать файл резервной копии для каждой базы данных**</span><span class="sxs-lookup"><span data-stu-id="65f7a-146">**Create a backup file for every database**</span></span>  
 <span data-ttu-id="65f7a-147">Создавать файл резервной копии в расположении, указанном в соответствующем окне папки.</span><span class="sxs-lookup"><span data-stu-id="65f7a-147">Create a backup file in the location specified in the folder box.</span></span> <span data-ttu-id="65f7a-148">Для каждой выбранной базы данных будет создан один файл.</span><span class="sxs-lookup"><span data-stu-id="65f7a-148">One file will be created for each database selected.</span></span>  
  
 <span data-ttu-id="65f7a-149">**Создавать вложенный каталог для каждой базы данных**</span><span class="sxs-lookup"><span data-stu-id="65f7a-149">**Create a sub-directory for each database**</span></span>  
 <span data-ttu-id="65f7a-150">Установите, чтобы поместить каждую базу данных в собственную вложенную папку.</span><span class="sxs-lookup"><span data-stu-id="65f7a-150">Select to place each database in a subfolder.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="65f7a-151">Хотя планы обслуживания могут создавать вложенные каталоги, задачи обслуживания не могут их удалять.</span><span class="sxs-lookup"><span data-stu-id="65f7a-151">Although maintenance plans can create subdirectories, maintenance tasks cannot delete subdirectories.</span></span> <span data-ttu-id="65f7a-152">Это снижает вероятность того, что злоумышленник сможет удалить файлы с помощью задачи «Очистка после обслуживания».</span><span class="sxs-lookup"><span data-stu-id="65f7a-152">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="65f7a-153">Подкаталог наследует разрешения от родительского каталога.</span><span class="sxs-lookup"><span data-stu-id="65f7a-153">The subdirectory inherits permissions from the parent directory.</span></span> <span data-ttu-id="65f7a-154">Ограничьте разрешения для предотвращения несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="65f7a-154">Restrict permissions to avoid unauthorized access.</span></span>  
  
 <span data-ttu-id="65f7a-155">**Папка**</span><span class="sxs-lookup"><span data-stu-id="65f7a-155">**Folder**</span></span>  
 <span data-ttu-id="65f7a-156">Укажите папку, в которой будут автоматически создаваться файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-156">Specify the folder to contain the automatically created database files.</span></span>  
  
 <span data-ttu-id="65f7a-157">**Расширение файла резервной копии**</span><span class="sxs-lookup"><span data-stu-id="65f7a-157">**Backup file extension**</span></span>  
 <span data-ttu-id="65f7a-158">Укажите расширение, которое должно использоваться для файлов резервных копий.</span><span class="sxs-lookup"><span data-stu-id="65f7a-158">Specify the extension to use for the backup files.</span></span> <span data-ttu-id="65f7a-159">Значение по умолчанию — **BAK**.</span><span class="sxs-lookup"><span data-stu-id="65f7a-159">The default is **.bak**.</span></span>  
  
 <span data-ttu-id="65f7a-160">**Проверять целостность резервной копии**</span><span class="sxs-lookup"><span data-stu-id="65f7a-160">**Verify backup integrity**</span></span>  
 <span data-ttu-id="65f7a-161">Проверка полноты резервного набора данных и читаемости всех томов.</span><span class="sxs-lookup"><span data-stu-id="65f7a-161">Verify that the backup set is complete and that all volumes are readable.</span></span>  
  
 <span data-ttu-id="65f7a-162">**Создать резервную копию заключительного фрагмента журнала и оставить базу данных в состоянии восстановления**</span><span class="sxs-lookup"><span data-stu-id="65f7a-162">**Back up the tail of the log, and leave the database in the restoring state**</span></span>  
 <span data-ttu-id="65f7a-163">Создайте резервную копию журналов в самом конце перед восстановлением базы данных.</span><span class="sxs-lookup"><span data-stu-id="65f7a-163">Perform a log backup as the last step before restoring a database.</span></span> <span data-ttu-id="65f7a-164">Дополнительные сведения см. в статье [Резервные копии заключительного фрагмента журнала (SQL Server)](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="65f7a-164">For more information, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="65f7a-165">**Установка сжатия резервной копии**</span><span class="sxs-lookup"><span data-stu-id="65f7a-165">**Set backup compression**</span></span>  
 <span data-ttu-id="65f7a-166">В выпуске [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (или более поздней версии) выберите одно из следующих значений параметра [backup compression](../backup-restore/backup-compression-sql-server.md) :</span><span class="sxs-lookup"><span data-stu-id="65f7a-166">In [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (or a later version), select one the following [backup compression](../backup-restore/backup-compression-sql-server.md) values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="65f7a-167">**Использовать параметр сервера по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="65f7a-167">**Use the default server setting**</span></span>|<span data-ttu-id="65f7a-168">Щелкните для использования настроек уровня сервера, установленных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65f7a-168">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="65f7a-169">Значения по умолчанию устанавливаются в параметре конфигурации сервера **backup compression default** .</span><span class="sxs-lookup"><span data-stu-id="65f7a-169">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="65f7a-170">Сведения о том, как просмотреть текущую настройку этого параметра, см. в разделе [Параметр конфигурации сервера "Просмотр или настройка параметра сжатия резервных копий по умолчанию"](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="65f7a-170">For information about how to view the current setting of this option,  see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="65f7a-171">**Сжимать резервные копии**</span><span class="sxs-lookup"><span data-stu-id="65f7a-171">**Compress backup**</span></span>|<span data-ttu-id="65f7a-172">Щелкните для сжатия резервной копии, независимо от уровня сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65f7a-172">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="65f7a-173">**\*\* Важно! \*\*** По умолчанию сжатие существенно повышает загрузку ЦП. Дополнительная нагрузка на ЦП может помешать выполнению параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="65f7a-173">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely affect concurrent operations.</span></span> <span data-ttu-id="65f7a-174">Поэтому может потребоваться создать сжатые резервные копии с низким приоритетом в сеансе, для которого использование ЦП ограничивается [регулятором ресурсов](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="65f7a-174">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="65f7a-175">Дополнительные сведения см. ниже в подразделе [Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (Transact-SQL)](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="65f7a-175">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="65f7a-176">**Не сжимать резервные копии**</span><span class="sxs-lookup"><span data-stu-id="65f7a-176">**Do not compress backup**</span></span>|<span data-ttu-id="65f7a-177">Щелкните для создания резервной копии без сжатия, независимо от уровня сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65f7a-177">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
 <span data-ttu-id="65f7a-178">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="65f7a-178">**View T-SQL**</span></span>  
 <span data-ttu-id="65f7a-179">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="65f7a-179">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65f7a-180">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="65f7a-180">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="65f7a-181">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="65f7a-181">New Connection Dialog Box</span></span>  
 <span data-ttu-id="65f7a-182">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="65f7a-182">**Connection name**</span></span>  
 <span data-ttu-id="65f7a-183">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="65f7a-183">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="65f7a-184">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="65f7a-184">**Select or enter a server name**</span></span>  
 <span data-ttu-id="65f7a-185">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="65f7a-185">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="65f7a-186">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="65f7a-186">**Refresh**</span></span>  
 <span data-ttu-id="65f7a-187">Обновите список доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="65f7a-187">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="65f7a-188">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="65f7a-188">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="65f7a-189">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="65f7a-189">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="65f7a-190">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="65f7a-190">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="65f7a-191">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] c проверкой подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="65f7a-191">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="65f7a-192">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="65f7a-192">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="65f7a-193">Подключиться к экземпляру компонента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] с использованием проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65f7a-193">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="65f7a-194">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="65f7a-194">This option is not available.</span></span>  
  
 <span data-ttu-id="65f7a-195">**User name**</span><span class="sxs-lookup"><span data-stu-id="65f7a-195">**User name**</span></span>  
 <span data-ttu-id="65f7a-196">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65f7a-196">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="65f7a-197">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="65f7a-197">This option is not available.</span></span>  
  
 <span data-ttu-id="65f7a-198">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="65f7a-198">**Password**</span></span>  
 <span data-ttu-id="65f7a-199">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="65f7a-199">Provide a password to use when authenticating.</span></span> <span data-ttu-id="65f7a-200">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="65f7a-200">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f7a-201">См. также:</span><span class="sxs-lookup"><span data-stu-id="65f7a-201">See Also</span></span>  
 [<span data-ttu-id="65f7a-202">BACKUP (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="65f7a-202">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  
  
