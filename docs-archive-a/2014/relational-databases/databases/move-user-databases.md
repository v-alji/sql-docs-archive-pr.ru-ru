---
title: Перемещение пользовательских баз данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- editions [SQL Server], moving databases between
- moving full-text catalogs
- scheduled disk maintenace [SQL Server]
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- moving user databases
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: ad9a4e92-13fb-457d-996a-66ffc2d55b79
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c2b82c3bec13c82aa30aebd175ef78f8136ee04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658813"
---
# <a name="move-user-databases"></a><span data-ttu-id="d1dd8-102">Перемещение пользовательских баз данных</span><span class="sxs-lookup"><span data-stu-id="d1dd8-102">Move User Databases</span></span>
  <span data-ttu-id="d1dd8-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]позволяет переносить в новое место файлы данных, журнала и полнотекстового каталога пользовательской базы данных; новое место указывается при помощи предложения FILENAME инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d1dd8-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move the data, log, and full-text catalog files of a user database to a new location by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="d1dd8-104">Этот метод подходит для перемещения файлов базы данных в пределах одного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1dd8-104">This method applies to moving database files within the same instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d1dd8-105">Для переноса базы данных на другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или другой сервер применяются операции [резервного копирования и восстановления](../backup-restore/back-up-and-restore-of-sql-server-databases.md) или [отключения и подключения](move-a-database-using-detach-and-attach-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d1dd8-105">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach operations](move-a-database-using-detach-and-attach-transact-sql.md).</span></span>  
  
## <a name="considerations"></a><span data-ttu-id="d1dd8-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="d1dd8-106">Considerations</span></span>  
 <span data-ttu-id="d1dd8-107">Чтобы обеспечить целостность работы пользователей и приложений при перемещении базы данных на другой экземпляр сервера, необходимо повторно создать некоторые или все метаданные базы данных.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-107">When you move a database onto another server instance, to provide a consistent experience to users and applications, you might have to re-create some or all the metadata for the database.</span></span> <span data-ttu-id="d1dd8-108">Дополнительные сведения см. в статье [Управление метаданными при обеспечении доступности базы данных на другом экземпляре сервера (SQL Server)](manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="d1dd8-108">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
 <span data-ttu-id="d1dd8-109">Некоторые функции компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] изменяют способ, с помощью которого [!INCLUDE[ssDE](../../includes/ssde-md.md)] хранит информацию в файлах базы данных.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-109">Some features of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] change the way that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores information in the database files.</span></span> <span data-ttu-id="d1dd8-110">Эти функции зависят от конкретных выпусков [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1dd8-110">These features are restricted to specific editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d1dd8-111">База данных, содержащая данные функции, не может быть перемещена в выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который их не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-111">A database that contains these features cannot be moved to an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that does not support them.</span></span> <span data-ttu-id="d1dd8-112">Используйте динамическое административное представление sys.dm_db_persisted_sku_features чтобы просмотреть список всех зависящих от выпуска функций, включенных в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-112">Use the sys.dm_db_persisted_sku_features dynamic management view to list all edition-specific features that are enabled in the current database.</span></span>  
  
 <span data-ttu-id="d1dd8-113">Для выполнения процедур, описанных в данном разделе, необходимо логическое имя файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-113">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="d1dd8-114">Это имя можно получить из столбца name представления каталога [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d1dd8-114">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="d1dd8-115">Начиная с [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], полнотекстовые каталоги интегрированы в базу данных, а не хранятся в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-115">Starting with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], full-text catalogs are integrated into the database rather than being stored in the file system.</span></span> <span data-ttu-id="d1dd8-116">Полнотекстовые каталоги теперь перемещаются автоматически при перемещении базы данных.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-116">The full-text catalogs now move automatically when you move a database.</span></span>  
  
## <a name="planned-relocation-procedure"></a><span data-ttu-id="d1dd8-117">Процедура запланированного перемещения</span><span class="sxs-lookup"><span data-stu-id="d1dd8-117">Planned Relocation Procedure</span></span>  
 <span data-ttu-id="d1dd8-118">Для запланированного перемещения файлов журнала или данных выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-118">To move a data or log file as part of a planned relocation, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d1dd8-119">Выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d1dd8-119">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET OFFLINE;  
    ```  
  
2.  <span data-ttu-id="d1dd8-120">Переместите файл или файлы в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-120">Move the file or files to the new location.</span></span>  
  
3.  <span data-ttu-id="d1dd8-121">Для каждого перемещенного файла выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d1dd8-121">For each file moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name, FILENAME = 'new_path\os_file_name' );  
    ```  
  
4.  <span data-ttu-id="d1dd8-122">Выполните следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d1dd8-122">Run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name SET ONLINE;  
    ```  
  
5.  <span data-ttu-id="d1dd8-123">Проверьте изменения в файле с помощью следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-123">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="relocation-for-scheduled-disk-maintenance"></a><span data-ttu-id="d1dd8-124">Перемещение для запланированного обслуживания дисков</span><span class="sxs-lookup"><span data-stu-id="d1dd8-124">Relocation for Scheduled Disk Maintenance</span></span>  
 <span data-ttu-id="d1dd8-125">Чтобы переместить файл во время процесса запланированного обслуживания дисков, необходимо выполнить нижеприведенные шаги.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-125">To relocate a file as part of a scheduled disk maintenance process, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d1dd8-126">Для каждого перемещаемого файла выполните следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-126">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
2.  <span data-ttu-id="d1dd8-127">Остановите работу экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или выключите систему для проведения работ по обслуживанию дисков.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-127">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="d1dd8-128">Дополнительные сведения см. в статье [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1dd8-128">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="d1dd8-129">Переместите файл или файлы в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-129">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="d1dd8-130">Перезапустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или сервер.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-130">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="d1dd8-131">Дополнительные сведения см. в разделе [Запуск, остановка, приостановка, возобновление и перезапуск ядра СУБД, агента SQL Server и обозревателя SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1dd8-131">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)</span></span>  
  
5.  <span data-ttu-id="d1dd8-132">Проверьте изменения в файле с помощью следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-132">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="failure-recovery-procedure"></a><span data-ttu-id="d1dd8-133">Процедура восстановления после сбоя</span><span class="sxs-lookup"><span data-stu-id="d1dd8-133">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="d1dd8-134">Если файл необходимо переместить в новое место из-за аппаратного сбоя, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-134">If a file must be moved because of a hardware failure, use the following steps to relocate the file to a new location.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d1dd8-135">Если базу данных запустить нельзя, она находится в подозрительном режиме или в невосстановленном состоянии, то файл может быть перемещен только членом предопределенной роли sysadmin.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-135">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="d1dd8-136">Остановите работу экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если он запущен.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-136">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="d1dd8-137">Запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в режиме восстановления «только master», запустив из командной строки одну из следующих команд.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-137">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span>  
  
    -   <span data-ttu-id="d1dd8-138">В случае с экземпляром по умолчанию (MSSQLSERVER) выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-138">For the default (MSSQLSERVER) instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="d1dd8-139">В случае с именованным экземпляром выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-139">For a named instance, run the following command.</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="d1dd8-140">Дополнительные сведения см. в статье [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1dd8-140">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="d1dd8-141">Для каждого перемещаемого файла используйте команды **sqlcmd** или [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] для выполнения следующей инструкции.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-141">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' );  
    ```  
  
     <span data-ttu-id="d1dd8-142">Дополнительные сведения об использовании программы **sqlcmd** см. в статье [Использование программы sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="d1dd8-142">For more information about how to use the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="d1dd8-143">Завершите работу программы **sqlcmd** или [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1dd8-143">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="d1dd8-144">Остановите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1dd8-144">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
6.  <span data-ttu-id="d1dd8-145">Переместите файл или файлы в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-145">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="d1dd8-146">Запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1dd8-146">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d1dd8-147">Например, выполните команду `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-147">For example, run: `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="d1dd8-148">Проверьте изменения в файле с помощью следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-148">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
## <a name="examples"></a><span data-ttu-id="d1dd8-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="d1dd8-149">Examples</span></span>  
 <span data-ttu-id="d1dd8-150">В следующем примере файл журнала базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] переносится в новое место во время запланированного перемещения.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-150">The following example moves the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] log file to a new location as part of a planned relocation.</span></span>  
  
```  
USE master;  
GO  
-- Return the logical file name.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
GO  
ALTER DATABASE AdventureWorks2012 SET OFFLINE;  
GO  
-- Physically move the file to a new location.  
-- In the following statement, modify the path specified in FILENAME to  
-- the new location of the file on your server.  
ALTER DATABASE AdventureWorks2012   
    MODIFY FILE ( NAME = AdventureWorks2012_Log,   
                  FILENAME = 'C:\NewLoc\AdventureWorks2012_Log.ldf');  
GO  
ALTER DATABASE AdventureWorks2012 SET ONLINE;  
GO  
--Verify the new location.  
SELECT name, physical_name AS CurrentLocation, state_desc  
FROM sys.master_files  
WHERE database_id = DB_ID(N'AdventureWorks2012')  
    AND type_desc = N'LOG';  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1dd8-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1dd8-151">See Also</span></span>  
 <span data-ttu-id="d1dd8-152">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d1dd8-152">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="d1dd8-153">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d1dd8-153">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="d1dd8-154">[Присоединение и отсоединение базы данных (SQL Server)](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d1dd8-154">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="d1dd8-155">[Перемещение системных баз данных](system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="d1dd8-155">[Move System Databases](system-databases.md) </span></span>  
 <span data-ttu-id="d1dd8-156">[Перемещение файлов базы данных](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="d1dd8-156">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="d1dd8-157">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d1dd8-157">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="d1dd8-158">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d1dd8-158">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="d1dd8-159">Запуск, остановка, приостановка, возобновление и перезапуск компонента Database Engine, агента SQL и службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1dd8-159">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
