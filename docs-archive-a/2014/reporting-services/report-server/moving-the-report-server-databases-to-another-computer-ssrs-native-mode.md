---
title: Перемещение баз данных сервера отчетов на другой компьютер (службы SSRS в собственном режиме) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 44a9854d-e333-44f6-bdc7-8837b9f34416
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49fd35f57cf783b262b3c690e3047e5f479ab193
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727914"
---
# <a name="moving-the-report-server-databases-to-another-computer-ssrs-native-mode"></a><span data-ttu-id="b9db2-102">Перемещение баз данных сервера отчетов на другой компьютер (собственный режим служб SSRS)</span><span class="sxs-lookup"><span data-stu-id="b9db2-102">Moving the Report Server Databases to Another Computer (SSRS Native Mode)</span></span>
  <span data-ttu-id="b9db2-103">Можно переместить базы данных сервера отчетов, используемые при установке, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] в экземпляр служб, расположенный на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b9db2-103">You can move the report server databases that are used in an installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] to an instance that is on a different computer.</span></span> <span data-ttu-id="b9db2-104">Базы данных reportserver и reportservertempdb должны перемещаться или копироваться вместе.</span><span class="sxs-lookup"><span data-stu-id="b9db2-104">Both the reportserver and reportservertempdb databases must be moved or copied together.</span></span> <span data-ttu-id="b9db2-105">Установка служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] требует наличия обеих баз данных. База данных reportservertempdb должна быть связана по имени с перемещаемой базой данных reportserver.</span><span class="sxs-lookup"><span data-stu-id="b9db2-105">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires both databases; the reportservertempdb database must be related by name to the primary reportserver database you are moving.</span></span>  
  
 <span data-ttu-id="b9db2-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.</span><span class="sxs-lookup"><span data-stu-id="b9db2-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="b9db2-107">Перемещение базы данных не влияет на запланированные операции, определенные в данный момент для элементов сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-107">Moving a database does not effect scheduled operations that are currently defined for report server items.</span></span>  
  
-   <span data-ttu-id="b9db2-108">Расписания будут созданы повторно при первом перезапуске службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-108">Schedules will be recreated the first time that you restart the Report Server service.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b9db2-109">, использующиеся для запуска расписания, будут созданы повторно в новом экземпляре базы данных.</span><span class="sxs-lookup"><span data-stu-id="b9db2-109">Agent jobs that are used to trigger a schedule will be recreated on the new database instance.</span></span> <span data-ttu-id="b9db2-110">Необязательно перемещать эти задания на новый компьютер, однако следует удалить задания на компьютере, на котором они больше не будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="b9db2-110">You do not have to move the jobs to the new computer, but you might want to delete jobs on the computer that will no longer be used.</span></span>  
  
-   <span data-ttu-id="b9db2-111">Подписки, кэшированные отчеты и моментальные снимки сохраняются в перемещенной базе данных.</span><span class="sxs-lookup"><span data-stu-id="b9db2-111">Subscriptions, cached reports, and snapshots are preserved in the moved database.</span></span> <span data-ttu-id="b9db2-112">Если моментальный снимок не получает обновленные данные после перемещения базы данных, отмените параметры моментального снимка в диспетчере отчетов, нажмите кнопку **Применить** , чтобы сохранить изменения, повторно создайте расписание и еще раз нажмите кнопку **Применить** , сохранив изменения.</span><span class="sxs-lookup"><span data-stu-id="b9db2-112">If a snapshot is not picking up refreshed data after the database is moved, clear the snapshot options in Report Manager, click **Apply** to save your changes, re-create the schedule, and click **Apply** again to save your changes.</span></span>  
  
-   <span data-ttu-id="b9db2-113">Временные данные отчета и пользовательского сеанса, хранящиеся в базе данных reportservertempdb, при перемещении этой базы данных сохраняются.</span><span class="sxs-lookup"><span data-stu-id="b9db2-113">Temporary report and user session data that is stored in reportservertempdb are persisted when you move that database.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b9db2-114">предусматривает несколько подходов к перемещению баз данных, включая резервное копирование и восстановление, присоединение и отсоединение, а также копирование.</span><span class="sxs-lookup"><span data-stu-id="b9db2-114">provides several approaches for moving databases, including backup and restore, attach and detach, and copy.</span></span> <span data-ttu-id="b9db2-115">Не все из них пригодны для переноса существующей базы данных на новый экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="b9db2-115">Not all approaches are appropriate for relocating an existing database to a new server instance.</span></span> <span data-ttu-id="b9db2-116">Подход, который следует использовать для перемещения базы данных сервера отчетов, зависит от требований к доступности системы.</span><span class="sxs-lookup"><span data-stu-id="b9db2-116">The approach that you should use to move the report server database will vary depending on your system availability requirements.</span></span> <span data-ttu-id="b9db2-117">Наиболее простой способ перемещения баз данных сервера отчетов состоит в их отсоединении и присоединении.</span><span class="sxs-lookup"><span data-stu-id="b9db2-117">The easiest way to move the report server databases is to attach and detach them.</span></span> <span data-ttu-id="b9db2-118">Однако такой подход требует, чтобы сервер отчетов во время отсоединения базы данных был переведен в режим «вне сети».</span><span class="sxs-lookup"><span data-stu-id="b9db2-118">However, this approach requires that you take the report server offline while you detach the database.</span></span> <span data-ttu-id="b9db2-119">Если нужно свести к минимуму перерывы в обслуживании, лучшим выбором будет резервное копирование и восстановление, хотя для выполнения этих операций потребуется запуск команд [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9db2-119">Backup and restore is a better choice if you want to minimize service disruptions, but you must run [!INCLUDE[tsql](../../includes/tsql-md.md)] commands to perform the operations.</span></span> <span data-ttu-id="b9db2-120">Не рекомендуется выполнять копирование базы данных (особенно с помощью мастера копирования базы данных), так как при этом в базе данных не сохраняются настройки разрешений.</span><span class="sxs-lookup"><span data-stu-id="b9db2-120">Copying the database is not recommended (specifically, by using the Copy Database Wizard); it does not preserve permission settings in the database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b9db2-121">Шаги, описанные в этом подразделе, следует выполнять только в том случае, если перемещение базы данных сервера отчетов является единственным изменением, которое вносится в текущую установку.</span><span class="sxs-lookup"><span data-stu-id="b9db2-121">The steps provided in this topic are recommended when relocating the report server database is the only change you are making to the existing installation.</span></span> <span data-ttu-id="b9db2-122">При миграции всей установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (то есть для перемещения базы данных и изменения удостоверения службы Windows сервера отчетов, которая использует эту базу данных) необходима повторная настройка соединения и сброс ключа шифрования.</span><span class="sxs-lookup"><span data-stu-id="b9db2-122">Migrating an entire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation (that is, moving the database and changing the identity of the Report Server Windows service that uses the database) requires connection reconfiguration and an encryption key reset.</span></span>  
  
## <a name="detaching-and-attaching-the-report-server-databases"></a><span data-ttu-id="b9db2-123">Отсоединение и присоединение баз данных сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="b9db2-123">Detaching and Attaching the Report Server Databases</span></span>  
 <span data-ttu-id="b9db2-124">Если сервер отчетов может быть переведен в режим «вне сети», можно отсоединить базы данных, чтобы переместить их на тот экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="b9db2-124">If you can take the report server offline, you can detach the databases to move them to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="b9db2-125">При таком подходе разрешения в базах данных сохраняются.</span><span class="sxs-lookup"><span data-stu-id="b9db2-125">This approach preserves permissions in the databases.</span></span> <span data-ttu-id="b9db2-126">Если используется база данных [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , необходимо переместить ее на другой экземпляр [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9db2-126">If you are using a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, you must move it to another [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance.</span></span> <span data-ttu-id="b9db2-127">После перемещения баз данных следует заново настроить соединение сервера отчетов с базой данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-127">After you move the databases, you must reconfigure the report server connection to the report server database.</span></span> <span data-ttu-id="b9db2-128">Если при масштабном развертывании запущено несколько серверов отчетов, необходимо заново настроить подключение к базе данных сервера отчетов для каждого сервера отчетов, входящего в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="b9db2-128">If you are running a scale-out deployment, you must reconfigure the report server database connection for each report server in the deployment.</span></span>  
  
 <span data-ttu-id="b9db2-129">Для перемещения баз данных выполните следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="b9db2-129">Use the following steps to move the databases:</span></span>  
  
1.  <span data-ttu-id="b9db2-130">Создайте резервную копию ключей шифрования для перемещаемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="b9db2-130">Backup the encryption keys for the report server database you want to move.</span></span> <span data-ttu-id="b9db2-131">Для этого можно использовать программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9db2-131">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool backup the keys.</span></span>  
  
2.  <span data-ttu-id="b9db2-132">Остановите службу сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-132">Stop the Report Server service.</span></span> <span data-ttu-id="b9db2-133">Для этого можно использовать программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9db2-133">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to stop the service.</span></span>  
  
3.  <span data-ttu-id="b9db2-134">Запустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и откройте соединение с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляром, на котором размещены базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-134">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and open a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server databases.</span></span>  
  
4.  <span data-ttu-id="b9db2-135">Щелкните правой кнопкой мыши базу данных сервера отчетов, укажите пункт "Задачи" и выберите команду **Отсоединить**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-135">Right-click the report server database, point to Tasks, and click **Detach**.</span></span> <span data-ttu-id="b9db2-136">Повторите этот шаг для временной базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-136">Repeat this step for the report server temporary database.</span></span>  
  
5.  <span data-ttu-id="b9db2-137">Скопируйте или переместите MDF- и LDF-файлы в папку данных экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="b9db2-137">Copy or move the .mdf and .ldf files to the Data folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="b9db2-138">Поскольку осуществляется перемещение двух баз данных, удостоверьтесь, что скопированы или перемещены все четыре файла.</span><span class="sxs-lookup"><span data-stu-id="b9db2-138">Because you are moving two databases, make sure that you move or copy all four files.</span></span>  
  
6.  <span data-ttu-id="b9db2-139">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]установите соединение с новым экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором будут размещены базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-139">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a connection to the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that will host the report server databases.</span></span>  
  
7.  <span data-ttu-id="b9db2-140">Щелкните правой кнопкой мыши узел "Базы данных" и выберите пункт **Присоединить**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-140">Right-click the Databases node, and then click **Attach**.</span></span>  
  
8.  <span data-ttu-id="b9db2-141">Нажмите кнопку **Добавить** , чтобы выбрать MDF- и LDF-файлы базы данных сервера отчетов, которые следует присоединить.</span><span class="sxs-lookup"><span data-stu-id="b9db2-141">Click **Add** to select the report server database .mdf and .ldf files that you want to attach.</span></span> <span data-ttu-id="b9db2-142">Повторите этот шаг для временной базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-142">Repeat this step for the report server temporary database.</span></span>  
  
9. <span data-ttu-id="b9db2-143">После присоединения баз данных убедитесь, что `RSExecRole` является ролью базы данных в базе данных сервера отчетов и временной базой данных.</span><span class="sxs-lookup"><span data-stu-id="b9db2-143">After the databases are attached, verify that the `RSExecRole` is a database role in the report server database and temporary database.</span></span> <span data-ttu-id="b9db2-144">`RSExecRole`в таблицах базы данных сервера отчетов должны быть установлены разрешения SELECT, INSERT, Update, DELETE и Reference, а также разрешения на выполнение хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="b9db2-144">`RSExecRole` must have select, insert, update, delete, and reference permissions on the report server database tables, and execute permissions on the stored procedures.</span></span> <span data-ttu-id="b9db2-145">Дополнительные сведения см. в разделе [Создание RSExecRole](../security/create-the-rsexecrole.md).</span><span class="sxs-lookup"><span data-stu-id="b9db2-145">For more information, see [Create the RSExecRole](../security/create-the-rsexecrole.md).</span></span>  
  
10. <span data-ttu-id="b9db2-146">Запустите программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и соединитесь с сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-146">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and open a connection to the report server.</span></span>  
  
11. <span data-ttu-id="b9db2-147">На странице «База данных» выберите новый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-147">On the Database page, select the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then click **Connect**.</span></span>  
  
12. <span data-ttu-id="b9db2-148">Выберите вновь перемещенную базу данных сервера отчетов и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-148">Select the report server database that you just moved, and then click **Apply**.</span></span>  
  
13. <span data-ttu-id="b9db2-149">На странице «Ключи шифрования» нажмите кнопку «Восстановить».</span><span class="sxs-lookup"><span data-stu-id="b9db2-149">On the Encryption Keys page, click Restore.</span></span> <span data-ttu-id="b9db2-150">Укажите файл, содержащий резервную копию ключей и пароль для разблокирования этого файла.</span><span class="sxs-lookup"><span data-stu-id="b9db2-150">Specify the file that contains the backup copy of the keys and the password to unlock the file.</span></span>  
  
14. <span data-ttu-id="b9db2-151">Перезапустите службу сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-151">Restart the Report Server service.</span></span>  
  
## <a name="backing-up-and-restoring-the-report-server-databases"></a><span data-ttu-id="b9db2-152">Резервное копирование и восстановление из копии баз данных сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="b9db2-152">Backing Up and Restoring the Report Server Databases</span></span>  
 <span data-ttu-id="b9db2-153">Если сервер отчетов нельзя перевести в режим «вне сети», для перемещения его баз данных можно использовать резервное копирование и восстановление.</span><span class="sxs-lookup"><span data-stu-id="b9db2-153">If you cannot take the report server offline, you can use backup and restore to relocate the report server databases.</span></span> <span data-ttu-id="b9db2-154">Чтобы выполнить резервное копирование и восстановление, необходимо использовать инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9db2-154">You must use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to do the backup and restore.</span></span> <span data-ttu-id="b9db2-155">После восстановления баз данных следует настроить сервер отчетов, чтобы он использовал базу данных на новом экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="b9db2-155">After you restore the databases, you must configure the report server to use the database on the new server instance.</span></span> <span data-ttu-id="b9db2-156">Дополнительные сведения см. в инструкциях, приведенных в конце этого подраздела.</span><span class="sxs-lookup"><span data-stu-id="b9db2-156">For more information, see the instructions at the end of this topic.</span></span>  
  
### <a name="using-backup-and-copy_only-to-backup-the-report-server-databases"></a><span data-ttu-id="b9db2-157">Использование для резервного копирования баз данных сервера отчетов инструкций BACKUP и COPY_ONLY</span><span class="sxs-lookup"><span data-stu-id="b9db2-157">Using BACKUP and COPY_ONLY to Backup the Report Server Databases</span></span>  
 <span data-ttu-id="b9db2-158">При резервном копировании баз данных установите аргумент COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="b9db2-158">When backing up the databases, set the COPY_ONLY argument.</span></span> <span data-ttu-id="b9db2-159">Убедитесь, что создаются резервные копии как баз данных, так и файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-159">Be sure to back up both of the databases and log files.</span></span>  
  
```  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServer  
   SET RECOVERY FULL  
  
-- If the ReportServerData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerData',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerData.bak'  
  
-- Create a logical backup device, ReportServerLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerLog.bak'  
  
-- Back up the full ReportServer database.  
BACKUP DATABASE ReportServer  
   TO ReportServerData  
   WITH COPY_ONLY  
  
-- Back up the ReportServer log.  
BACKUP LOG ReportServer  
   TO ReportServerLog  
   WITH COPY_ONLY  
  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServerTempdb  
   SET RECOVERY FULL  
  
-- If the ReportServerTempDBData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBData',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBData.bak'  
  
-- Create a logical backup device, ReportServerTempDBLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBLog.bak'  
  
-- Back up the full ReportServerTempDB database.  
BACKUP DATABASE ReportServerTempDB  
   TO ReportServerTempDBData  
   WITH COPY_ONLY  
  
-- Back up the ReportServerTempDB log.  
BACKUP LOG ReportServerTempDB  
   TO ReportServerTempDBLog  
   WITH COPY_ONLY  
```  
  
### <a name="using-restore-and-move-to-relocate-the-report-server-databases"></a><span data-ttu-id="b9db2-160">Использование для перемещения баз данных сервера отчетов инструкций RESTORE и MOVE</span><span class="sxs-lookup"><span data-stu-id="b9db2-160">Using RESTORE and MOVE to Relocate the Report Server Databases</span></span>  
 <span data-ttu-id="b9db2-161">При восстановлении баз данных из копии обязательно включите аргумент MOVE, чтобы можно было указать путь.</span><span class="sxs-lookup"><span data-stu-id="b9db2-161">When restoring the databases, be sure to include the MOVE argument so that you can specify a path.</span></span> <span data-ttu-id="b9db2-162">Для первоначального восстановления используйте аргумент NORECOVERY, это позволяет сохранить базу данных в состоянии RESTORING и даст время для просмотра резервных копий журналов, чтобы определить, какой из них следует восстанавливать.</span><span class="sxs-lookup"><span data-stu-id="b9db2-162">Use the NORECOVERY argument to perform the initial restore; this keeps the database in a RESTORING state, giving you time to review log backups to determine which one to restore.</span></span> <span data-ttu-id="b9db2-163">В качестве последнего шага следует повторить операцию RESTORE с аргументом RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b9db2-163">The final step repeats the RESTORE operation with the RECOVERY argument.</span></span>  
  
 <span data-ttu-id="b9db2-164">В аргументе MOVE используется логическое имя файла данных.</span><span class="sxs-lookup"><span data-stu-id="b9db2-164">The MOVE argument uses the logical name of the data file.</span></span> <span data-ttu-id="b9db2-165">Чтобы определить логическое имя, выполните следующую инструкцию: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="b9db2-165">To find the logical name, execute the following statement: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="b9db2-166">Следующие примеры включают аргумент FILE, что позволяет указать позицию файла журнала, который требуется восстановить.</span><span class="sxs-lookup"><span data-stu-id="b9db2-166">The following examples include the FILE argument so that you can specify the file position of the log file to restore.</span></span> <span data-ttu-id="b9db2-167">Чтобы определить позицию файла, выполните следующую инструкцию: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="b9db2-167">To find the file position, execute the following statement: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="b9db2-168">При восстановлении из копии файлов базы данных и журнала каждую операцию RESTORE следует выполнять отдельно.</span><span class="sxs-lookup"><span data-stu-id="b9db2-168">When restoring the database and log files, you should run each RESTORE operation separately.</span></span>  
  
```  
-- Restore the report server database and move to new instance folder   
RESTORE DATABASE ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore the report server log file to new instance folder   
RESTORE LOG ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore and move the report server temporary database  
RESTORE DATABASE ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Restore the temporary database log file to new instance folder   
RESTORE LOG ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServer  
   WITH RECOVERY  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServerTempDB  
   WITH RECOVERY  
GO  
```  
  
### <a name="how-to-configure-the-report-server-database-connection"></a><span data-ttu-id="b9db2-169">Настройка подключения к базе данных сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="b9db2-169">How to Configure the Report Server Database Connection</span></span>  
  
1.  <span data-ttu-id="b9db2-170">Запустите диспетчер конфигурации служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и подключитесь к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-170">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and open a connection to the report server.</span></span>  
  
2.  <span data-ttu-id="b9db2-171">На странице «База данных» нажмите кнопку **Изменить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-171">On the Database page, click **Change Database**.</span></span> <span data-ttu-id="b9db2-172">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-172">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="b9db2-173">Щелкните **Выбрать существующую базу данных сервера отчетов**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-173">Click **Choose an existing report server database**.</span></span> <span data-ttu-id="b9db2-174">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-174">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="b9db2-175">Выберите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором находится база данных сервера отчетов, и нажмите кнопку **Проверить соединение**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-175">Select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that now hosts the report server database and click **Test Connection**.</span></span> <span data-ttu-id="b9db2-176">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-176">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="b9db2-177">В поле «Имя базы данных» выберите нужную базу данных сервера отчета.</span><span class="sxs-lookup"><span data-stu-id="b9db2-177">In Database Name, select the report server database that you want to use.</span></span> <span data-ttu-id="b9db2-178">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-178">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b9db2-179">В поле «Учетные данные» укажите учетные данные, которые сервер отчетов будет использовать для подключения к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-179">In Credentials, specify the credentials that the report server will use to connect to the report server database.</span></span> <span data-ttu-id="b9db2-180">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-180">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b9db2-181">Нажмите кнопку **Далее** , затем — кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b9db2-181">Click **Next** and then **Finish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9db2-182">Установка служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] требует, чтобы экземпляр компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] включал роль `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="b9db2-182">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance include the `RSExecRole` role.</span></span> <span data-ttu-id="b9db2-183">Создание роли, регистрация имени входа и назначения ролей происходят, когда с помощью программы настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] устанавливается подключение к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="b9db2-183">Role creation, login registration, and role assignments occur when you set the report server database connection through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="b9db2-184">При иных подходах к настройке соединения (особенно если используется программа командной строки rsconfig.exe) сервер отчетов окажется в неработоспособном состоянии.</span><span class="sxs-lookup"><span data-stu-id="b9db2-184">If you use alternate approaches (specifically, if you use the rsconfig.exe command prompt utility) to configure the connection, the report server will not be in a working state.</span></span> <span data-ttu-id="b9db2-185">Чтобы сервер отчетов стал доступным, возможно, придется записать код инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="b9db2-185">You might have to write WMI code to make the report server available.</span></span> <span data-ttu-id="b9db2-186">Дополнительные сведения см. в разделе [Доступ к поставщику WMI для служб Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="b9db2-186">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9db2-187">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9db2-187">See Also</span></span>  
 <span data-ttu-id="b9db2-188">[Создание роли RSExecRole](../security/create-the-rsexecrole.md) </span><span class="sxs-lookup"><span data-stu-id="b9db2-188">[Create the RSExecRole](../security/create-the-rsexecrole.md) </span></span>  
 <span data-ttu-id="b9db2-189">[Запуск и остановка службы сервера отчетов](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="b9db2-189">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 <span data-ttu-id="b9db2-190">[Настройка подключения к базе данных сервера отчетов &#40;службы SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b9db2-190">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="b9db2-191">[Настройка учетной записи автоматического выполнения &#40;Configuration Manager SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b9db2-191">[Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="b9db2-192">[Использование диспетчера конфигурации служб Reporting Services (собственный режим)](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="b9db2-192">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="b9db2-193">[Программа rsconfig &#40;службы SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b9db2-193">[rsconfig Utility &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span></span>  
 <span data-ttu-id="b9db2-194">[Настройка ключей шифрования и управление ими &#40;служб SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span><span class="sxs-lookup"><span data-stu-id="b9db2-194">[Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span></span>  
 [<span data-ttu-id="b9db2-195">База данных сервера отчетов (службы Reporting Services в собственном режиме)</span><span class="sxs-lookup"><span data-stu-id="b9db2-195">Report Server Database &#40;SSRS Native Mode&#41;</span></span>](report-server-database-ssrs-native-mode.md)  
  
  
