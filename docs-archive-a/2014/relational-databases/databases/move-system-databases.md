---
title: Перемещение системных баз данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- moving system databases
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- tempdb database [SQL Server], moving
- system databases [SQL Server], moving
- scheduled disk maintenace [SQL Server]
- moving databases
- msdb database [SQL Server], moving
- moving database files
- relocating database files
- planned database relocations [SQL Server]
- master database [SQL Server], moving
- model database [SQL Server], moving
- Resource database [SQL Server]
- databases [SQL Server], moving
ms.assetid: 72bb62ee-9602-4f71-be51-c466c1670878
author: stevestein
ms.author: sstein
ms.openlocfilehash: 748d781d6bbefb0dc710427a34ebd71ec7037fdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752227"
---
# <a name="move-system-databases"></a><span data-ttu-id="48834-102">Перемещение системных баз данных</span><span class="sxs-lookup"><span data-stu-id="48834-102">Move System Databases</span></span>
  <span data-ttu-id="48834-103">В этом разделе описано, как в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]перемещают системные базы данных.</span><span class="sxs-lookup"><span data-stu-id="48834-103">This topic describes how to move system databases in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="48834-104">Эта операция может пригодиться в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="48834-104">Moving system databases may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="48834-105">Восстановление после сбоя.</span><span class="sxs-lookup"><span data-stu-id="48834-105">Failure recovery.</span></span> <span data-ttu-id="48834-106">Например, база данных находится в подозрительном режиме, или ее работа была прекращена из-за сбоя оборудования;</span><span class="sxs-lookup"><span data-stu-id="48834-106">For example, the database is in suspect mode or has shut down because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="48834-107">Плановое перемещение.</span><span class="sxs-lookup"><span data-stu-id="48834-107">Planned relocation.</span></span>  
  
-   <span data-ttu-id="48834-108">Перемещение для запланированного обслуживания дисков.</span><span class="sxs-lookup"><span data-stu-id="48834-108">Relocation for scheduled disk maintenance.</span></span>  
  
 <span data-ttu-id="48834-109">Следующие процедуры применяются для перемещения файлов баз данных в пределах одного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48834-109">The following procedures apply to moving database files within the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="48834-110">Перемещение базы данных на другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или на другой сервер возможно через операции [резервного копирования и восстановления](../backup-restore/back-up-and-restore-of-sql-server-databases.md) или [отсоединения и присоединения](move-a-database-using-detach-and-attach-transact-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="48834-110">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use the [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach](move-a-database-using-detach-and-attach-transact-sql.md) operations.</span></span>  
  
 <span data-ttu-id="48834-111">Для выполнения процедур, описанных в данном разделе, необходимо логическое имя файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="48834-111">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="48834-112">Это имя можно получить из столбца name представления каталога [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="48834-112">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48834-113">При перемещении системной базы данных с последующим перестроением базы данных master необходимо заново переместить системную базу данных, поскольку операция перестроения устанавливает все системные базы данных в расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48834-113">If you move a system database and later rebuild the master database, you must move the system database again because the rebuild operation installs all system databases to their default location.</span></span>  
  
##  <a name="in-this-topic"></a><a name="Intro"></a><span data-ttu-id="48834-114">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="48834-114">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="48834-115">Запланированное перемещение и запланированная процедура обслуживания диска</span><span class="sxs-lookup"><span data-stu-id="48834-115">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>](#Planned)  
  
-   [<span data-ttu-id="48834-116">Процедура восстановления после сбоя</span><span class="sxs-lookup"><span data-stu-id="48834-116">Failure Recovery Procedure</span></span>](#Failure)  
  
-   [<span data-ttu-id="48834-117">Перемещение базы данных master</span><span class="sxs-lookup"><span data-stu-id="48834-117">Moving the master Database</span></span>](#master)  
  
-   [<span data-ttu-id="48834-118">Перемещение базы данных Resource</span><span class="sxs-lookup"><span data-stu-id="48834-118">Moving the Resource Database</span></span>](#Resource)  
  
-   [<span data-ttu-id="48834-119">Дальнейшие действия. После перемещения всех системных баз данных</span><span class="sxs-lookup"><span data-stu-id="48834-119">Follow-up: After Moving All System Databases</span></span>](#Follow)  
  
-   [<span data-ttu-id="48834-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="48834-120">Examples</span></span>](#Examples)  
  
##  <a name="planned-relocation-and-scheduled-disk-maintenance-procedure"></a><a name="Planned"></a> <span data-ttu-id="48834-121">Запланированное перемещение и процедура запланированного обслуживания диска</span><span class="sxs-lookup"><span data-stu-id="48834-121">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>  
 <span data-ttu-id="48834-122">Чтобы переместить данные системной базы данных или файл журнала в рамках запланированного перемещения (операции запланированного обслуживания), следуйте следующим указаниям:</span><span class="sxs-lookup"><span data-stu-id="48834-122">To move a system database data or log file as part of a planned relocation or scheduled maintenance operation, follow these steps.</span></span> <span data-ttu-id="48834-123">Данная процедура применима ко всем системным базам данных, кроме master и Resource.</span><span class="sxs-lookup"><span data-stu-id="48834-123">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
1.  <span data-ttu-id="48834-124">Для каждого перемещаемого файла выполните следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="48834-124">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
2.  <span data-ttu-id="48834-125">Остановите работу экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или выключите систему для проведения работ по обслуживанию дисков.</span><span class="sxs-lookup"><span data-stu-id="48834-125">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="48834-126">Дополнительные сведения см. в статье [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="48834-126">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="48834-127">Переместите файл или файлы в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="48834-127">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="48834-128">Перезапустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или сервер.</span><span class="sxs-lookup"><span data-stu-id="48834-128">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="48834-129">Дополнительные сведения см. в статье [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="48834-129">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
5.  <span data-ttu-id="48834-130">Проверьте изменения в файле с помощью следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="48834-130">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
 <span data-ttu-id="48834-131">Если база данных msdb перемещена, а экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настроен для компонента [Database Mail](../database-mail/database-mail.md), выполните следующие дополнительные шаги.</span><span class="sxs-lookup"><span data-stu-id="48834-131">If the msdb database is moved and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for [Database Mail](../database-mail/database-mail.md), complete these additional steps.</span></span>  
  
1.  <span data-ttu-id="48834-132">С помощью следующего запроса убедитесь, что в базе данных msdb включен компонент [!INCLUDE[ssSB](../../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48834-132">Verify that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] is enabled for the msdb database by running the following query.</span></span>  
  
    ```  
    SELECT is_broker_enabled   
    FROM sys.databases  
    WHERE name = N'msdb';  
    ```  
  
     <span data-ttu-id="48834-133">Дополнительные сведения о включении [!INCLUDE[ssSB](../../../includes/sssb-md.md)]см. в разделе [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql)перемещают системные базы данных.</span><span class="sxs-lookup"><span data-stu-id="48834-133">For more information about enabling [!INCLUDE[ssSB](../../../includes/sssb-md.md)], see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
2.  <span data-ttu-id="48834-134">Отправкой тестового сообщения проверьте работоспособность компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="48834-134">Verify that Database Mail is working by sending a test mail.</span></span>  
  
##  <a name="failure-recovery-procedure"></a><a name="Failure"></a> <span data-ttu-id="48834-135">Процедура восстановления после сбоя</span><span class="sxs-lookup"><span data-stu-id="48834-135">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="48834-136">Если нужно перенести файл из-за сбоя оборудования, необходимо выполнить приведенные ниже действия для его перемещения на новое место.</span><span class="sxs-lookup"><span data-stu-id="48834-136">If a file must be moved because of a hardware failure, follow these steps to relocate the file to a new location.</span></span> <span data-ttu-id="48834-137">Данная процедура применима ко всем системным базам данных, кроме master и Resource.</span><span class="sxs-lookup"><span data-stu-id="48834-137">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="48834-138">Если базу данных запустить нельзя, она находится в подозрительном режиме или в невосстановленном состоянии, то файл может быть перемещен только членом предопределенной роли sysadmin.</span><span class="sxs-lookup"><span data-stu-id="48834-138">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="48834-139">Остановите работу экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , если он запущен.</span><span class="sxs-lookup"><span data-stu-id="48834-139">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="48834-140">Запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в режиме восстановления «только master», запустив из командной строки одну из следующих команд.</span><span class="sxs-lookup"><span data-stu-id="48834-140">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span> <span data-ttu-id="48834-141">В задаваемых для них параметрах учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="48834-141">The parameters specified in these commands are case sensitive.</span></span> <span data-ttu-id="48834-142">Команды завершаются ошибкой, если параметры заданы не так, как показано.</span><span class="sxs-lookup"><span data-stu-id="48834-142">The commands fail when the parameters are not specified as shown.</span></span>  
  
    -   <span data-ttu-id="48834-143">В случае с экземпляром по умолчанию (MSSQLSERVER) запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48834-143">For the default (MSSQLSERVER) instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="48834-144">В случае с именованным экземпляром запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48834-144">For a named instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="48834-145">Дополнительные сведения см. в статье [Iniciar, parar, pausar, retomar e reiniciar os serviços SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="48834-145">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="48834-146">Для каждого перемещаемого файла используйте команды **sqlcmd** или [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] для выполнения следующей инструкции.</span><span class="sxs-lookup"><span data-stu-id="48834-146">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
     <span data-ttu-id="48834-147">Дополнительные сведения об использовании программы **sqlcmd** см. в статье [Использование программы sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="48834-147">For more information about using the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="48834-148">Завершите работу программы **sqlcmd** или [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48834-148">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="48834-149">Остановите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48834-149">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="48834-150">Например, выполните команду `NET STOP MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="48834-150">For example, run `NET STOP MSSQLSERVER`.</span></span>  
  
6.  <span data-ttu-id="48834-151">Переместите файл или файлы в новое расположение.</span><span class="sxs-lookup"><span data-stu-id="48834-151">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="48834-152">Повторно запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48834-152">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="48834-153">Например, выполните команду `NET START MSSQLSERVER`.</span><span class="sxs-lookup"><span data-stu-id="48834-153">For example, run `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="48834-154">Проверьте изменения в файле с помощью следующего запроса.</span><span class="sxs-lookup"><span data-stu-id="48834-154">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
##  <a name="moving-the-master-database"></a><a name="master"></a> <span data-ttu-id="48834-155">Перемещение базы данных master</span><span class="sxs-lookup"><span data-stu-id="48834-155">Moving the master Database</span></span>  
 <span data-ttu-id="48834-156">Чтобы переместить базу данных master, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="48834-156">To move the master database, follow these steps.</span></span>  
  
1.  <span data-ttu-id="48834-157">В меню **Пуск** выберите **Все программы**, укажите **Microsoft SQL Server**, затем **Средства настройки**и выберите пункт **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="48834-157">From the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="48834-158">Находясь в узле **Службы SQL Server** , щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , например **SQL Server (MSSQLSERVER)** , и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="48834-158">In the **SQL Server Services** node, right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (for example, **SQL Server (MSSQLSERVER)**) and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="48834-159">В диалоговом окне \*\*Свойства SQL Server ( \*\*\*имя_экземпляра \***)** перейдите на вкладку **Параметры запуска** .</span><span class="sxs-lookup"><span data-stu-id="48834-159">In the **SQL Server (***instance_name***) Properties** dialog box, click the **Startup Parameters** tab.</span></span>  
  
4.  <span data-ttu-id="48834-160">В поле **Существующие параметры** выберите параметр -d, чтобы переместить файл данных master.</span><span class="sxs-lookup"><span data-stu-id="48834-160">In the **Existing parameters** box, select the -d parameter to move the master data file.</span></span> <span data-ttu-id="48834-161">Нажмите **Обновить** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="48834-161">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="48834-162">В поле **Укажите параметр запуска** задайте новый путь к базе данных master.</span><span class="sxs-lookup"><span data-stu-id="48834-162">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
5.  <span data-ttu-id="48834-163">В поле **Существующие параметры** выберите параметр -l, чтобы переместить файл журнала master.</span><span class="sxs-lookup"><span data-stu-id="48834-163">In the **Existing parameters** box, select the -l parameter to move the master log file.</span></span> <span data-ttu-id="48834-164">Нажмите **Обновить** для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="48834-164">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="48834-165">В поле **Укажите параметр запуска** задайте новый путь к базе данных master.</span><span class="sxs-lookup"><span data-stu-id="48834-165">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
     <span data-ttu-id="48834-166">Значение параметра для файла данных должно соответствовать параметру `-d` , а значение для файла журнала — параметру `-l` .</span><span class="sxs-lookup"><span data-stu-id="48834-166">The parameter value for the data file must follow the `-d` parameter and the value for the log file must follow the `-l` parameter.</span></span> <span data-ttu-id="48834-167">В следующем примере показаны значения параметров для указания местоположения файла базы данных master по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48834-167">The following example shows the parameter values for the default location of the master data file.</span></span>  
  
     `-dC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\master.mdf`  
  
     `-lC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\mastlog.ldf`  
  
     <span data-ttu-id="48834-168">Если планируется переместить файл данных базы данных master в расположение `E:\SQLData`, значения параметра будут изменены следующим образом.</span><span class="sxs-lookup"><span data-stu-id="48834-168">If the planned relocation for the master data file is `E:\SQLData`, the parameter values would be changed as follows:</span></span>  
  
     `-dE:\SQLData\master.mdf`  
  
     `-lE:\SQLData\mastlog.ldf`  
  
6.  <span data-ttu-id="48834-169">Остановите работу экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , щелкнув правой кнопкой мыши имя экземпляра и выбрав команду **Остановить**.</span><span class="sxs-lookup"><span data-stu-id="48834-169">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by right-clicking the instance name and choosing **Stop**.</span></span>  
  
7.  <span data-ttu-id="48834-170">Переместите файлы master.mdf и mastlog.ldf на новое место.</span><span class="sxs-lookup"><span data-stu-id="48834-170">Move the master.mdf and mastlog.ldf files to the new location.</span></span>  
  
8.  <span data-ttu-id="48834-171">Повторно запустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48834-171">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="48834-172">Проверьте правильность изменений для базы данных master, выполнив следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="48834-172">Verify the file change for the master database by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID('master');  
    GO  
    ```  
  
##  <a name="moving-the-resource-database"></a><a name="Resource"></a> <span data-ttu-id="48834-173">Перемещение базы данных Resource</span><span class="sxs-lookup"><span data-stu-id="48834-173">Moving the Resource Database</span></span>  
 <span data-ttu-id="48834-174">База данных находится в каталоге \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span><span class="sxs-lookup"><span data-stu-id="48834-174">The location of the Resource database is \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span></span> <span data-ttu-id="48834-175">Эту базу данных нельзя переместить.</span><span class="sxs-lookup"><span data-stu-id="48834-175">The database cannot be moved.</span></span>  
  
##  <a name="follow-up-after-moving-all-system-databases"></a><a name="Follow"></a> <span data-ttu-id="48834-176">Дальнейшие действия. После перемещения всех системных баз данных</span><span class="sxs-lookup"><span data-stu-id="48834-176">Follow-up: After Moving All System Databases</span></span>  
 <span data-ttu-id="48834-177">Если все системные базы данных перемещаются на новый диск или том либо на другой сервер с другой буквой диска, выполните следующие обновления.</span><span class="sxs-lookup"><span data-stu-id="48834-177">If you have moved all of the system databases to a new drive or volume or to another server with a different drive letter, make the following updates.</span></span>  
  
-   <span data-ttu-id="48834-178">Измените путь к журналу агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="48834-178">Change the SQL Server Agent log path.</span></span> <span data-ttu-id="48834-179">Если этого не сделать, то агент SQL Server не сможет запуститься.</span><span class="sxs-lookup"><span data-stu-id="48834-179">If you do not update this path, SQL Server Agent will fail to start.</span></span>  
  
-   <span data-ttu-id="48834-180">Измените расположение по умолчанию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="48834-180">Change the database default location.</span></span> <span data-ttu-id="48834-181">Создание новой базы данных может завершиться ошибкой, если буква диска и путь, указанные в качестве места расположения по умолчанию, не существуют.</span><span class="sxs-lookup"><span data-stu-id="48834-181">Creating a new database may fail if the drive letter and path specified as the default location do not exist.</span></span>  
  
#### <a name="change-the-sql-server-agent-log-path"></a><span data-ttu-id="48834-182">Измените путь к журналу агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="48834-182">Change the SQL Server Agent Log Path</span></span>  
  
1.  <span data-ttu-id="48834-183">В среде SQL Server Management Studio в обозревателе объектов разверните узел **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="48834-183">From SQL Server Management Studio, in Object Explorer, expand **SQL Server Agent**.</span></span>  
  
2.  <span data-ttu-id="48834-184">Щелкните правой кнопкой мыши **Журналы ошибок** и выберите пункт **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="48834-184">Right-click **Error Logs** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="48834-185">В диалоговом окне **Настройка журналов ошибок агента SQL Server** задайте новое расположение для файла SQLAGENT.OUT.</span><span class="sxs-lookup"><span data-stu-id="48834-185">In the **Configure SQL Server Agent Error Logs** dialog box, specify the new location of the SQLAGENT.OUT file.</span></span> <span data-ttu-id="48834-186">Расположение по умолчанию — C:\Program Files\Microsoft SQL Server\MSSQL12. <instance_name> \MSSQL\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="48834-186">The default location is C:\Program Files\Microsoft SQL Server\MSSQL12.<instance_name>\MSSQL\Log\\.</span></span>  
  
#### <a name="change-the-database-default-location"></a><span data-ttu-id="48834-187">Измените расположение по умолчанию для базы данных</span><span class="sxs-lookup"><span data-stu-id="48834-187">Change the database default location</span></span>  
  
1.  <span data-ttu-id="48834-188">В среде SQL Server Management Studio в обозревателе объектов щелкните правой кнопкой мыши сервер SQL Server и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="48834-188">From SQL Server Management Studio, in Object Explorer, right-click the SQL Server server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="48834-189">В диалоговом окне **Свойства сервера** выберите пункт **Настройки базы данных**.</span><span class="sxs-lookup"><span data-stu-id="48834-189">In the **Server Properties** dialog box, select **Database Settings**.</span></span>  
  
3.  <span data-ttu-id="48834-190">На панели **Места хранения, используемые базой данных по умолчанию**можно просмотреть текущие места хранения, используемые по умолчанию для новых файлов данных и файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="48834-190">Under **Database Default Locations**, browse to the new location for both the data and log files.</span></span>  
  
4.  <span data-ttu-id="48834-191">Остановите и запустите службу SQL Server, чтобы завершить изменение.</span><span class="sxs-lookup"><span data-stu-id="48834-191">Stop and start the SQL Server service to complete the change.</span></span>  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="48834-192">Примеры</span><span class="sxs-lookup"><span data-stu-id="48834-192">Examples</span></span>  
  
### <a name="a-moving-the-tempdb-database"></a><span data-ttu-id="48834-193">A.</span><span class="sxs-lookup"><span data-stu-id="48834-193">A.</span></span> <span data-ttu-id="48834-194">Перемещение базы данных tempdb</span><span class="sxs-lookup"><span data-stu-id="48834-194">Moving the tempdb database</span></span>  
 <span data-ttu-id="48834-195">В следующем примере показано перемещение файлов базы данных `tempdb` и журнала на новое место в рамках запланированного перемещения.</span><span class="sxs-lookup"><span data-stu-id="48834-195">The following example moves the `tempdb` data and log files to a new location as part of a planned relocation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48834-196">Поскольку база данных tempdb создается повторно при каждом запуске экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , то нет необходимости физически переносить файлы данных и журнала.</span><span class="sxs-lookup"><span data-stu-id="48834-196">Because tempdb is re-created each time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, you do not have to physically move the data and log files.</span></span> <span data-ttu-id="48834-197">Файлы создаются в новом месте во время перезагрузки службы на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="48834-197">The files are created in the new location when the service is restarted in step 3.</span></span> <span data-ttu-id="48834-198">До перезагрузки службы база данных tempdb продолжает использовать файлы данных и файл журнала, расположенные в существующем месте.</span><span class="sxs-lookup"><span data-stu-id="48834-198">Until the service is restarted, tempdb continues to use the data and log files in existing location.</span></span>  
  
1.  <span data-ttu-id="48834-199">Определение логических имен файлов базы данных `tempdb` и их текущего местоположения на диске.</span><span class="sxs-lookup"><span data-stu-id="48834-199">Determine the logical file names of the `tempdb` database and their current location on the disk.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    GO  
    ```  
  
2.  <span data-ttu-id="48834-200">Измените местоположение каждого файла с помощью `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="48834-200">Change the location of each file by using `ALTER DATABASE`.</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = tempdev, FILENAME = 'E:\SQLData\tempdb.mdf');  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = templog, FILENAME = 'F:\SQLLog\templog.ldf');  
    GO  
    ```  
  
3.  <span data-ttu-id="48834-201">Остановите и перезапустите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48834-201">Stop and restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="48834-202">Проверьте изменение файла.</span><span class="sxs-lookup"><span data-stu-id="48834-202">Verify the file change.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    ```  
  
5.  <span data-ttu-id="48834-203">Удалите файлы `tempdb.mdf` и `templog.ldf` из исходного местоположения.</span><span class="sxs-lookup"><span data-stu-id="48834-203">Delete the `tempdb.mdf` and `templog.ldf` files from the original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48834-204">См. также:</span><span class="sxs-lookup"><span data-stu-id="48834-204">See Also</span></span>  
 <span data-ttu-id="48834-205">[База данных Resource](resource-database.md) </span><span class="sxs-lookup"><span data-stu-id="48834-205">[Resource Database](resource-database.md) </span></span>  
 <span data-ttu-id="48834-206">[База данных tempdb](tempdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="48834-206">[tempdb Database](tempdb-database.md) </span></span>  
 <span data-ttu-id="48834-207">[База данных master](master-database.md) </span><span class="sxs-lookup"><span data-stu-id="48834-207">[master Database](master-database.md) </span></span>  
 <span data-ttu-id="48834-208">[База данных msdb](msdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="48834-208">[msdb Database](msdb-database.md) </span></span>  
 <span data-ttu-id="48834-209">[База данных model](model-database.md) </span><span class="sxs-lookup"><span data-stu-id="48834-209">[model Database](model-database.md) </span></span>  
 <span data-ttu-id="48834-210">[Перемещение пользовательских баз данных](move-user-databases.md) </span><span class="sxs-lookup"><span data-stu-id="48834-210">[Move User Databases](move-user-databases.md) </span></span>  
 <span data-ttu-id="48834-211">[Перемещение файлов базы данных](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="48834-211">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="48834-212">[Запуск, остановка, приостановка, возобновление и перезапуск ядра СУБД, агента SQL Server и обозревателя SQL Server](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="48834-212">[Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span></span>  
 <span data-ttu-id="48834-213">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48834-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="48834-214">Перестроение системных баз данных</span><span class="sxs-lookup"><span data-stu-id="48834-214">Rebuild System Databases</span></span>](system-databases.md)  
  
  
