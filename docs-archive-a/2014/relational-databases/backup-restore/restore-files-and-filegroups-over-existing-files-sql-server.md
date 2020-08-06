---
title: Восстановление файлов и файловых групп поверх существующих файлов (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
- overwriting filegroups
- overwriting files
ms.assetid: 517e07eb-9685-4b06-90af-b1cc496700b7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc72ae3ae2472fe579755fa624e9af6953c7aed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658837"
---
# <a name="restore-files-and-filegroups-over-existing-files-sql-server"></a><span data-ttu-id="7b892-102">Восстановление файлов и файловых групп поверх существующих файлов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7b892-102">Restore Files and Filegroups over Existing Files (SQL Server)</span></span>
  <span data-ttu-id="7b892-103">В этом разделе описывается восстановление файлов и файловых групп для существующих файлов в среде [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b892-103">This topic describes how to restore files and filegroups over existing files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7b892-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7b892-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7b892-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7b892-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7b892-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7b892-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7b892-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7b892-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7b892-108">**Восстановление файлов и файловых групп поверх существующих с помощью:**</span><span class="sxs-lookup"><span data-stu-id="7b892-108">**To restore files and filegroups over existing files, using:**</span></span>  
  
     [<span data-ttu-id="7b892-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b892-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7b892-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b892-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b892-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7b892-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7b892-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="7b892-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7b892-113">Системный администратор, восстанавливающий файлы и файловые группы, должен быть единственным лицом, использующим восстанавливаемую базу данных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="7b892-113">The system administrator who is restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="7b892-114">Инструкция RESTORE недопустима в явной или неявной транзакции.</span><span class="sxs-lookup"><span data-stu-id="7b892-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="7b892-115">Перед началом восстановления файлов по модели полного восстановления или модели восстановления с неполным протоколированием необходимо выполнить резервное копирование активного журнала транзакций (который называется заключительным фрагментом журнала).</span><span class="sxs-lookup"><span data-stu-id="7b892-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="7b892-116">Дополнительные сведения см. в статье [Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="7b892-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="7b892-117">Чтобы восстановить зашифрованную базу данных, необходимо иметь доступ к сертификату или асимметричному ключу, который использовался для шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="7b892-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="7b892-118">Без сертификата или асимметричного ключа восстановить базу данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="7b892-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="7b892-119">Поэтому сертификат, используемый для шифрования ключа шифрования базы данных, должен храниться в течение всего времени, пока есть необходимость в резервной копии.</span><span class="sxs-lookup"><span data-stu-id="7b892-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="7b892-120">Дополнительные сведения см. в статье [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="7b892-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7b892-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="7b892-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7b892-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="7b892-122">Permissions</span></span>  
 <span data-ttu-id="7b892-123">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="7b892-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="7b892-124">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="7b892-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="7b892-125">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="7b892-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="7b892-126">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="7b892-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7b892-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b892-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="7b892-128">Восстановление файлов и файловых групп поверх существующих файлов</span><span class="sxs-lookup"><span data-stu-id="7b892-128">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="7b892-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], разверните его, а затем разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="7b892-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="7b892-130">Щелкните правой кнопкой мыши нужную базу данных, наведите указатель на пункт **Задачи**, а затем выберите пункты **Восстановить**и **Файлы и файловые группы**.</span><span class="sxs-lookup"><span data-stu-id="7b892-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="7b892-131">На странице **Общие** в списке **В базу данных** введите имя восстанавливаемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="7b892-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="7b892-132">Можно ввести новую базу данных или выбрать уже существующую из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="7b892-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="7b892-133">Список включает все базы данных на сервере кроме системных баз данных **master** и **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="7b892-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="7b892-134">Чтобы указать источник и расположение восстанавливаемых резервных наборов данных, выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="7b892-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="7b892-135">**Из базы данных**</span><span class="sxs-lookup"><span data-stu-id="7b892-135">**From database**</span></span>  
  
         <span data-ttu-id="7b892-136">Введите имя базы данных в списке.</span><span class="sxs-lookup"><span data-stu-id="7b892-136">Enter a database name in the list box.</span></span> <span data-ttu-id="7b892-137">Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .</span><span class="sxs-lookup"><span data-stu-id="7b892-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="7b892-138">**С устройства**</span><span class="sxs-lookup"><span data-stu-id="7b892-138">**From device**</span></span>  
  
         <span data-ttu-id="7b892-139">Нажмите кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="7b892-139">Click the browse button.</span></span> <span data-ttu-id="7b892-140">В диалоговом окне **Указание устройств резервного копирования** выберите один из перечисленных типов устройств в списке **Тип носителя резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="7b892-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="7b892-141">Чтобы выбрать одно или несколько устройств в списке **Носитель резервной копии** , нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7b892-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="7b892-142">После добавления нужных устройств в списке **Носитель резервной копии** нажмите кнопку **ОК** для возвращения на страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="7b892-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="7b892-143">В сетке **Выберите резервные наборы данных для восстановления** выберите нужные резервные наборы.</span><span class="sxs-lookup"><span data-stu-id="7b892-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="7b892-144">В этой сетке отображаются резервные копии, доступные в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="7b892-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="7b892-145">По умолчанию предлагается план восстановления.</span><span class="sxs-lookup"><span data-stu-id="7b892-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="7b892-146">Чтобы переопределить предложенный план восстановления, можно изменить выбранные элементы в сетке.</span><span class="sxs-lookup"><span data-stu-id="7b892-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="7b892-147">Если выбор каких-то резервных копий отменяется, то автоматически отменяется и выбор зависящих от них резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7b892-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="7b892-148">Заголовок столбца</span><span class="sxs-lookup"><span data-stu-id="7b892-148">Column head</span></span>|<span data-ttu-id="7b892-149">Значения</span><span class="sxs-lookup"><span data-stu-id="7b892-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="7b892-150">**Восстановление**</span><span class="sxs-lookup"><span data-stu-id="7b892-150">**Restore**</span></span>|<span data-ttu-id="7b892-151">Установленные флажки обозначают резервные наборы данных, отмеченные для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7b892-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="7b892-152">**имя**;</span><span class="sxs-lookup"><span data-stu-id="7b892-152">**Name**</span></span>|<span data-ttu-id="7b892-153">Имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="7b892-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="7b892-154">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="7b892-154">**File Type**</span></span>|<span data-ttu-id="7b892-155">Задает тип данных в резервной копии: **Данные**, **Журнал** или **Данные Filestream**.</span><span class="sxs-lookup"><span data-stu-id="7b892-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="7b892-156">Данные, содержащиеся в таблицах, хранятся в файлах типа **Данные** .</span><span class="sxs-lookup"><span data-stu-id="7b892-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="7b892-157">Данные журнала транзакций хранятся в файлах типа **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="7b892-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="7b892-158">Данные больших двоичных объектов (BLOB), которые хранятся в файловой системе, находятся в файлах типа **Данные Filestream** .</span><span class="sxs-lookup"><span data-stu-id="7b892-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="7b892-159">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7b892-159">**Type**</span></span>|<span data-ttu-id="7b892-160">Тип выполняемого резервного копирования: **Полное**, **Разностное**или **Журнал транзакций**.</span><span class="sxs-lookup"><span data-stu-id="7b892-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="7b892-161">**Server**</span><span class="sxs-lookup"><span data-stu-id="7b892-161">**Server**</span></span>|<span data-ttu-id="7b892-162">Имя экземпляра ядра СУБД, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7b892-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="7b892-163">**Логическое имя файла**</span><span class="sxs-lookup"><span data-stu-id="7b892-163">**File Logical Name**</span></span>|<span data-ttu-id="7b892-164">Логическое имя файла.</span><span class="sxs-lookup"><span data-stu-id="7b892-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="7b892-165">**База данных**</span><span class="sxs-lookup"><span data-stu-id="7b892-165">**Database**</span></span>|<span data-ttu-id="7b892-166">Имя базы данных, участвовавшей в операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7b892-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="7b892-167">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="7b892-167">**Start Date**</span></span>|<span data-ttu-id="7b892-168">Дата и время начала операции резервного копирования, указанные в региональных настройках клиента.</span><span class="sxs-lookup"><span data-stu-id="7b892-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="7b892-169">**Дата завершения**</span><span class="sxs-lookup"><span data-stu-id="7b892-169">**Finish Date**</span></span>|<span data-ttu-id="7b892-170">Дата и время завершения операции резервного копирования, указанные в формате, соответствующем региональным настройкам клиента.</span><span class="sxs-lookup"><span data-stu-id="7b892-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="7b892-171">**Размер**</span><span class="sxs-lookup"><span data-stu-id="7b892-171">**Size**</span></span>|<span data-ttu-id="7b892-172">Размер резервного набора данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="7b892-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="7b892-173">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="7b892-173">**User Name**</span></span>|<span data-ttu-id="7b892-174">Имя пользователя, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7b892-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="7b892-175">На панели **Выбор страницы** щелкните **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="7b892-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="7b892-176">На панели **Параметры восстановления** выберите пункт **Перезаписать существующую базу данных (WITH REPLACE)** .</span><span class="sxs-lookup"><span data-stu-id="7b892-176">In the **Restore options** panel, select **Overwrite the existing database (WITH REPLACE)**.</span></span> <span data-ttu-id="7b892-177">Операция восстановления перезаписывает все существующие базы данных и связанные с ними файлы, даже если база данных или файл с указанным именем уже существуют.</span><span class="sxs-lookup"><span data-stu-id="7b892-177">The restore operation overwrites any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7b892-178">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b892-178">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups-over-existing-files"></a><span data-ttu-id="7b892-179">Восстановление файлов и файловых групп поверх существующих файлов</span><span class="sxs-lookup"><span data-stu-id="7b892-179">To restore files and filegroups over existing files</span></span>  
  
1.  <span data-ttu-id="7b892-180">Выполните инструкцию RESTORE DATABASE для восстановления резервной копии файлов и файловых групп, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="7b892-180">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="7b892-181">Имя базы данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="7b892-181">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="7b892-182">Устройство резервного копирования, откуда будет восстановлена полная резервная копия.</span><span class="sxs-lookup"><span data-stu-id="7b892-182">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="7b892-183">предложение FILE для каждого восстанавливаемого файла;</span><span class="sxs-lookup"><span data-stu-id="7b892-183">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="7b892-184">предложение FILEGROUP для каждой восстанавливаемой файловой группы;</span><span class="sxs-lookup"><span data-stu-id="7b892-184">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="7b892-185">параметр REPLACE для указания возможности восстановления каждого файла поверх существующих файлов, имеющих то же имя и место размещения;</span><span class="sxs-lookup"><span data-stu-id="7b892-185">The REPLACE option to specify that each file can be restored over existing files of the same name and location.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="7b892-186">Параметр REPLACE следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="7b892-186">Use the REPLACE option cautiously.</span></span> <span data-ttu-id="7b892-187">Дополнительные сведения см. в разделе .</span><span class="sxs-lookup"><span data-stu-id="7b892-187">For more information, see .</span></span>  
  
    -   <span data-ttu-id="7b892-188">Параметр NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="7b892-188">The NORECOVERY option.</span></span> <span data-ttu-id="7b892-189">(если файлы не изменялись со времени создания резервной копии, укажите предложение RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="7b892-189">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="7b892-190">Если файлы были изменены после создания резервной копии, выполните инструкцию RESTORE LOG для применения резервной копии журнала транзакций, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="7b892-190">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="7b892-191">Имя базы данных, к которой будет применен журнал транзакций.</span><span class="sxs-lookup"><span data-stu-id="7b892-191">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="7b892-192">Устройство резервного копирования, с которого будет восстановлена резервная копия журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="7b892-192">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="7b892-193">Предложение NORECOVERY, если существует другая резервная копия журналов транзакций для применения после текущего; в противном случае укажите предложение RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="7b892-193">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="7b892-194">Резервные копии журналов транзакций, в случае их использования, должны включать в себя промежуток времени, в течение которого создавались резервные копии файлов и файловых групп.</span><span class="sxs-lookup"><span data-stu-id="7b892-194">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="7b892-195">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7b892-195">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="7b892-196">В данном примере показано восстановление файлов и файловых групп для базы данных `MyNwind` и замена всех существующих файлов, имеющих то же имя.</span><span class="sxs-lookup"><span data-stu-id="7b892-196">The following example restores the files and filegroups for the `MyNwind` database, and replaces any existing files of the same name.</span></span> <span data-ttu-id="7b892-197">Два журнала транзакций также будут применены при восстановлении базы данных до текущего момента.</span><span class="sxs-lookup"><span data-stu-id="7b892-197">Two transaction logs will also be applied to restore the database to the current time.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyNwind.  
RESTORE DATABASE MyNwind  
   FILE = 'MyNwind_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyNwind_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   REPLACE;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyNwind  
   FROM MyNwind_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b892-198">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b892-198">See Also</span></span>  
 <span data-ttu-id="7b892-199">[Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="7b892-199">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="7b892-200">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b892-200">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="7b892-201">[Восстановление файлов и файловых групп (SQL Server)](restore-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7b892-201">[Restore Files and Filegroups &#40;SQL Server&#41;](restore-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="7b892-202">Копирование баз данных путем создания и восстановления резервных копий</span><span class="sxs-lookup"><span data-stu-id="7b892-202">Copy Databases with Backup and Restore</span></span>](../databases/copy-databases-with-backup-and-restore.md)  
  
  
