---
title: Восстановление файлов и файловых групп (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restorefilesandfilegrps.general.f1
- sql12.swb.restorefilesandfilegrps.options.f1
- sql12.swb.bselectfilegrpsfiles.f1
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], restoring files and filegroups
- restoring [SQL Server], files
ms.assetid: 72603b21-3065-4b56-8b01-11b707911b05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2576f1326cb50fa197b1623aaa1326d70137823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731742"
---
# <a name="restore-files-and-filegroups-sql-server"></a><span data-ttu-id="c8735-102">Восстановление файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c8735-102">Restore Files and Filegroups (SQL Server)</span></span>
  <span data-ttu-id="c8735-103">В этом разделе описывается восстановление файлов и файловых групп в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8735-103">This topic describes how to restore files and filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c8735-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c8735-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c8735-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c8735-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c8735-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c8735-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="c8735-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c8735-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c8735-108">**Восстановление файлов и файловых групп с помощью следующих средств**</span><span class="sxs-lookup"><span data-stu-id="c8735-108">**To restore files and filegroups, using:**</span></span>  
  
     [<span data-ttu-id="c8735-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8735-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c8735-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8735-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c8735-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c8735-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c8735-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c8735-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c8735-113">Системный администратор, восстанавливающий файлы и файловые группы, должен быть единственным лицом, использующим восстанавливаемую базу данных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c8735-113">The system administrator restoring the files and filegroups must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="c8735-114">Инструкция RESTORE недопустима в явной или неявной транзакции.</span><span class="sxs-lookup"><span data-stu-id="c8735-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="c8735-115">При использовании простой модели восстановления файл должен принадлежать к файловой группе, находящейся в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c8735-115">Under the simple recovery model, the file must belong to a read-only filegroup.</span></span>  
  
-   <span data-ttu-id="c8735-116">Перед началом восстановления файлов по модели полного восстановления или модели восстановления с неполным протоколированием необходимо выполнить резервное копирование активного журнала транзакций (который называется заключительным фрагментом журнала).</span><span class="sxs-lookup"><span data-stu-id="c8735-116">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="c8735-117">Дополнительные сведения см. в статье [Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="c8735-117">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c8735-118">Чтобы восстановить зашифрованную базу данных, необходимо иметь доступ к сертификату или асимметричному ключу, который использовался для шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="c8735-118">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="c8735-119">Без сертификата или асимметричного ключа восстановить базу данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="c8735-119">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="c8735-120">Поэтому сертификат, используемый для шифрования ключа шифрования базы данных, должен храниться в течение всего времени, пока есть необходимость в резервной копии.</span><span class="sxs-lookup"><span data-stu-id="c8735-120">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="c8735-121">Дополнительные сведения см. в статье [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="c8735-121">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c8735-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="c8735-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c8735-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="c8735-123">Permissions</span></span>  
 <span data-ttu-id="c8735-124">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="c8735-124">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="c8735-125">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="c8735-125">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="c8735-126">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="c8735-126">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="c8735-127">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="c8735-127">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c8735-128">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8735-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="c8735-129">Восстановление файлов и файловых групп</span><span class="sxs-lookup"><span data-stu-id="c8735-129">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="c8735-130">После подключения к соответствующему экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]в обозревателе объектов разверните дерево сервера, щелкнув имя сервера.</span><span class="sxs-lookup"><span data-stu-id="c8735-130">After you connect to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="c8735-131">Разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="c8735-131">Expand **Databases**.</span></span> <span data-ttu-id="c8735-132">В зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных**и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="c8735-132">Depending on the database, either select a user database or expand **System Databases**, and then select a system database.</span></span>  
  
3.  <span data-ttu-id="c8735-133">Щелкните правой кнопкой мыши базу данных, укажите на пункт **Задачи**и щелкните **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="c8735-133">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="c8735-134">Щелкните **Файлы и файловые группы**, после чего откроется диалоговое окно **Восстановление файлов и файловых групп** .</span><span class="sxs-lookup"><span data-stu-id="c8735-134">Click **Files and Filegroups**, which opens the **Restore Files and Filegroups** dialog box.</span></span>  
  
5.  <span data-ttu-id="c8735-135">На странице **Общие** в списке **В базу данных** введите имя восстанавливаемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="c8735-135">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="c8735-136">Можно ввести новую базу данных или выбрать уже существующую из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="c8735-136">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="c8735-137">Список включает все базы данных на сервере кроме системных баз данных **master** и **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="c8735-137">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
6.  <span data-ttu-id="c8735-138">Чтобы указать источник и расположение восстанавливаемых резервных наборов данных, выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="c8735-138">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="c8735-139">**Из базы данных**</span><span class="sxs-lookup"><span data-stu-id="c8735-139">**From database**</span></span>  
  
         <span data-ttu-id="c8735-140">Введите имя базы данных в списке.</span><span class="sxs-lookup"><span data-stu-id="c8735-140">Enter a database name in the list box.</span></span> <span data-ttu-id="c8735-141">Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .</span><span class="sxs-lookup"><span data-stu-id="c8735-141">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="c8735-142">**С устройства**</span><span class="sxs-lookup"><span data-stu-id="c8735-142">**From device**</span></span>  
  
         <span data-ttu-id="c8735-143">Нажмите кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="c8735-143">Click the browse button.</span></span> <span data-ttu-id="c8735-144">В диалоговом окне **Указание устройств резервного копирования** выберите один из перечисленных типов устройств в списке **Тип носителя резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="c8735-144">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="c8735-145">Чтобы выбрать одно или несколько устройств в списке **Носитель резервной копии** , нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c8735-145">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="c8735-146">После добавления нужных устройств в списке **Носитель резервной копии** нажмите кнопку **ОК** для возвращения на страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="c8735-146">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
7.  <span data-ttu-id="c8735-147">В сетке **Выберите резервные наборы данных для восстановления** выберите нужные резервные наборы.</span><span class="sxs-lookup"><span data-stu-id="c8735-147">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="c8735-148">В этой сетке отображаются резервные копии, доступные в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="c8735-148">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="c8735-149">По умолчанию предлагается план восстановления.</span><span class="sxs-lookup"><span data-stu-id="c8735-149">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="c8735-150">Чтобы переопределить предложенный план восстановления, можно изменить выбранные элементы в сетке.</span><span class="sxs-lookup"><span data-stu-id="c8735-150">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="c8735-151">Если выбор каких-то резервных копий отменяется, то автоматически отменяется и выбор зависящих от них резервных копий.</span><span class="sxs-lookup"><span data-stu-id="c8735-151">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="c8735-152">Заголовок столбца</span><span class="sxs-lookup"><span data-stu-id="c8735-152">Column head</span></span>|<span data-ttu-id="c8735-153">Значения</span><span class="sxs-lookup"><span data-stu-id="c8735-153">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="c8735-154">**Восстановление**</span><span class="sxs-lookup"><span data-stu-id="c8735-154">**Restore**</span></span>|<span data-ttu-id="c8735-155">Установленные флажки обозначают резервные наборы данных, отмеченные для восстановления.</span><span class="sxs-lookup"><span data-stu-id="c8735-155">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="c8735-156">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c8735-156">**Name**</span></span>|<span data-ttu-id="c8735-157">Имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="c8735-157">The name of the backup set.</span></span>|  
    |<span data-ttu-id="c8735-158">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="c8735-158">**File Type**</span></span>|<span data-ttu-id="c8735-159">Задает тип данных в резервной копии: **Данные**, **Журнал** или **Данные Filestream**.</span><span class="sxs-lookup"><span data-stu-id="c8735-159">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="c8735-160">Данные, содержащиеся в таблицах, хранятся в файлах типа **Данные** .</span><span class="sxs-lookup"><span data-stu-id="c8735-160">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="c8735-161">Данные журнала транзакций хранятся в файлах типа **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="c8735-161">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="c8735-162">Данные больших двоичных объектов (BLOB), которые хранятся в файловой системе, находятся в файлах типа **Данные Filestream** .</span><span class="sxs-lookup"><span data-stu-id="c8735-162">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="c8735-163">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c8735-163">**Type**</span></span>|<span data-ttu-id="c8735-164">Тип выполняемого резервного копирования: **Полное**, **Разностное**или **Журнал транзакций**.</span><span class="sxs-lookup"><span data-stu-id="c8735-164">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="c8735-165">**Server**</span><span class="sxs-lookup"><span data-stu-id="c8735-165">**Server**</span></span>|<span data-ttu-id="c8735-166">Имя экземпляра ядра СУБД, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c8735-166">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="c8735-167">**Логическое имя файла**</span><span class="sxs-lookup"><span data-stu-id="c8735-167">**File Logical Name**</span></span>|<span data-ttu-id="c8735-168">Логическое имя файла.</span><span class="sxs-lookup"><span data-stu-id="c8735-168">The logical name of the file.</span></span>|  
    |<span data-ttu-id="c8735-169">**База данных**</span><span class="sxs-lookup"><span data-stu-id="c8735-169">**Database**</span></span>|<span data-ttu-id="c8735-170">Имя базы данных, участвовавшей в операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c8735-170">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="c8735-171">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="c8735-171">**Start Date**</span></span>|<span data-ttu-id="c8735-172">Дата и время начала операции резервного копирования, указанные в региональных настройках клиента.</span><span class="sxs-lookup"><span data-stu-id="c8735-172">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="c8735-173">**Дата завершения**</span><span class="sxs-lookup"><span data-stu-id="c8735-173">**Finish Date**</span></span>|<span data-ttu-id="c8735-174">Дата и время завершения операции резервного копирования, указанные в формате, соответствующем региональным настройкам клиента.</span><span class="sxs-lookup"><span data-stu-id="c8735-174">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="c8735-175">**Размер**</span><span class="sxs-lookup"><span data-stu-id="c8735-175">**Size**</span></span>|<span data-ttu-id="c8735-176">Размер резервного набора данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="c8735-176">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="c8735-177">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="c8735-177">**User Name**</span></span>|<span data-ttu-id="c8735-178">Имя пользователя, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="c8735-178">The name of the user who performed the backup operation.</span></span>|  
  
8.  <span data-ttu-id="c8735-179">Для просмотра или выбора дополнительных параметров нажмите кнопку **Параметры** на панели **Выбор страницы**.</span><span class="sxs-lookup"><span data-stu-id="c8735-179">To view or select the advanced options, click **Options** in the **Select a page pane**.</span></span>  
  
9. <span data-ttu-id="c8735-180">На панели **Параметры восстановления** можно выбрать любой из следующих параметров, если он подходит к данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="c8735-180">In the **Restore options** panel, you can choose any of the following options, if appropriate for your situation.</span></span>  
  
     <span data-ttu-id="c8735-181">**Восстановление файловой группы**</span><span class="sxs-lookup"><span data-stu-id="c8735-181">**Restore as filegroup**</span></span>  
     <span data-ttu-id="c8735-182">Указывает, что восстанавливается вся файловая группа.</span><span class="sxs-lookup"><span data-stu-id="c8735-182">Indicates that an entire filegroup is being restored.</span></span>  
  
     <span data-ttu-id="c8735-183">**Перезаписать существующую базу данных**</span><span class="sxs-lookup"><span data-stu-id="c8735-183">**Overwrite the existing database**</span></span>  
     <span data-ttu-id="c8735-184">Указывает, что операция восстановления должна переписать все существующие базы данных и связанные с ними файлы, даже если база данных или файл с указанным именем уже существуют.</span><span class="sxs-lookup"><span data-stu-id="c8735-184">Specifies that the restore operation should overwrite any existing databases and their related files, even if another database or file already exists with the same name.</span></span>  
  
     <span data-ttu-id="c8735-185">Выбор этой функции равнозначен использованию параметра REPLACE в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8735-185">Selecting this option is equivalent to using the REPLACE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="c8735-186">**Выдавать приглашение перед восстановлением каждой резервной копии**</span><span class="sxs-lookup"><span data-stu-id="c8735-186">**Prompt before restoring each backup**</span></span>  
     <span data-ttu-id="c8735-187">Запрашивает подтверждение перед восстановлением из копии каждого резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="c8735-187">Asks you for confirmation before restoring each backup set.</span></span>  
  
     <span data-ttu-id="c8735-188">Этот параметр особенно полезен, когда для использования различных наборов носителей необходимо менять ленты (например, если на сервере существует одно ленточное устройство).</span><span class="sxs-lookup"><span data-stu-id="c8735-188">This option is particularly useful where you must swap tapes for different media sets, such as when the server has one tape device.</span></span>  
  
     <span data-ttu-id="c8735-189">**Ограничить доступ к восстановленной базе данных**</span><span class="sxs-lookup"><span data-stu-id="c8735-189">**Restrict access to the restored database**</span></span>  
     <span data-ttu-id="c8735-190">Доступ к восстановленной базе данных будет только у пользователей **db_owner**, **dbcreator**или **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="c8735-190">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
     <span data-ttu-id="c8735-191">Выбор этой функции равнозначен использованию параметра RESTRICTED_USER в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8735-191">Selecting this option is synonymous to using the RESTRICTED_USER option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
10. <span data-ttu-id="c8735-192">По желанию можно восстановить базу данных в новое местоположение, задав новое назначение для каждого файла в сетке **Восстановить файлы базы данных как** .</span><span class="sxs-lookup"><span data-stu-id="c8735-192">Optionally, you can restore the database to a new location by specifying a new restore destination for each file in the **Restore database files as** grid.</span></span>  
  
    |<span data-ttu-id="c8735-193">Заголовок столбца</span><span class="sxs-lookup"><span data-stu-id="c8735-193">Column head</span></span>|<span data-ttu-id="c8735-194">Значения</span><span class="sxs-lookup"><span data-stu-id="c8735-194">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="c8735-195">**Имя исходного файла**</span><span class="sxs-lookup"><span data-stu-id="c8735-195">**Original File Name**</span></span>|<span data-ttu-id="c8735-196">Полный путь исходного файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="c8735-196">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="c8735-197">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="c8735-197">**File Type**</span></span>|<span data-ttu-id="c8735-198">Задает тип данных в резервной копии: **Данные**, **Журнал** или **Данные Filestream**.</span><span class="sxs-lookup"><span data-stu-id="c8735-198">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="c8735-199">Данные, содержащиеся в таблицах, хранятся в файлах типа **Данные** .</span><span class="sxs-lookup"><span data-stu-id="c8735-199">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="c8735-200">Данные журнала транзакций хранятся в файлах типа **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="c8735-200">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="c8735-201">Данные больших двоичных объектов (BLOB), которые хранятся в файловой системе, находятся в файлах типа **Данные Filestream** .</span><span class="sxs-lookup"><span data-stu-id="c8735-201">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="c8735-202">**Восстановить как**</span><span class="sxs-lookup"><span data-stu-id="c8735-202">**Restore As**</span></span>|<span data-ttu-id="c8735-203">Полный путь к файлу базы данных, который нужно восстановить.</span><span class="sxs-lookup"><span data-stu-id="c8735-203">The full path of the database file to be restored.</span></span> <span data-ttu-id="c8735-204">Чтобы указать новый восстанавливаемый файл, щелкните текстовое поле и измените предложенные путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="c8735-204">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="c8735-205">Изменение пути или имени файла в столбце **Восстановить как** равнозначно использованию параметра MOVE в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8735-205">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
11. <span data-ttu-id="c8735-206">В качестве значения параметра **Состояние восстановления** укажите состояние базы данных после операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="c8735-206">The **Recovery state** panel determines the state of the database after the restore operation.</span></span>  
  
     <span data-ttu-id="c8735-207">**Оставить базу данных готовой к использованию, выполнив откат незафиксированных транзакций. Невозможно восстановить дополнительные журналы транзакций. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="c8735-207">**Leave the database ready for use by rolling back the uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
     <span data-ttu-id="c8735-208">Восстанавливает базу данных.</span><span class="sxs-lookup"><span data-stu-id="c8735-208">Recovers the database.</span></span> <span data-ttu-id="c8735-209">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c8735-209">This is the default behavior.</span></span> <span data-ttu-id="c8735-210">Выберите этот параметр для восстановления всех необходимых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="c8735-210">Choose this option only if you are restoring all of the necessary backups now.</span></span> <span data-ttu-id="c8735-211">Этот параметр равнозначен указанию предложения WITH RECOVERY в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8735-211">This option is equivalent to specifying WITH RECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="c8735-212">**Оставить базу данных в нерабочем состоянии и не выполнять откат незавершенных транзакций. Можно восстановить дополнительные журналы транзакций. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="c8735-212">**Leave the database non-operational, and don't roll back the uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
     <span data-ttu-id="c8735-213">Оставляет базу данных в состоянии восстановления.</span><span class="sxs-lookup"><span data-stu-id="c8735-213">Leaves the database in the restoring state.</span></span> <span data-ttu-id="c8735-214">Чтобы восстановить базу данных, необходимо выполнить еще одно восстановление с использованием предыдущего параметра RESTORE WITH RECOVERY (см. выше).</span><span class="sxs-lookup"><span data-stu-id="c8735-214">To recover the database, you will need to perform another restore using the preceding RESTORE WITH RECOVERY option (see above).</span></span> <span data-ttu-id="c8735-215">Этот параметр равнозначен указанию предложения WITH NORECOVERY в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8735-215">This option is equivalent to specifying WITH NORECOVERY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="c8735-216">Если выбран этот параметр, то параметр **Сохранить настройки репликации** недоступен.</span><span class="sxs-lookup"><span data-stu-id="c8735-216">If you select this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
     <span data-ttu-id="c8735-217">**Оставить базу данных в режиме «только для чтения». Выполнить откат незавершенных транзакций с сохранением операции отката в файле, чтобы можно было отменить операцию восстановления. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="c8735-217">**Leave the database in read-only mode. Roll back the uncommitted transactions, but save the rollback operation in a file so the recovery effects can be undone. (RESTORE WITH STANDBY)**</span></span>  
     <span data-ttu-id="c8735-218">Оставляет базу данных в резервном состоянии.</span><span class="sxs-lookup"><span data-stu-id="c8735-218">Leaves the database in a standby state.</span></span> <span data-ttu-id="c8735-219">Этот параметр равнозначен указанию предложения WITH STANDBY в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8735-219">This option is equivalent to specifying WITH STANDBY in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>  
  
     <span data-ttu-id="c8735-220">При выборе этого параметра необходимо указать резервный файл.</span><span class="sxs-lookup"><span data-stu-id="c8735-220">Choosing this option requires that you specify a standby file.</span></span>  
  
     <span data-ttu-id="c8735-221">**Файл отмены отката**</span><span class="sxs-lookup"><span data-stu-id="c8735-221">**Rollback undo file**</span></span>  
     <span data-ttu-id="c8735-222">Укажите имя резервного файла в текстовом поле **Файл отмены отката** .</span><span class="sxs-lookup"><span data-stu-id="c8735-222">Specify a standby file name in the **Rollback undo file** text box.</span></span> <span data-ttu-id="c8735-223">Этот параметр необходим, если нужно оставить базу данных в режиме «только для чтения» (RESTORE WITH STANDBY).</span><span class="sxs-lookup"><span data-stu-id="c8735-223">This option is required if you leave the database in read-only mode (RESTORE WITH STANDBY).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c8735-224">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8735-224">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-and-filegroups"></a><span data-ttu-id="c8735-225">Восстановление файлов и файловых групп</span><span class="sxs-lookup"><span data-stu-id="c8735-225">To restore files and filegroups</span></span>  
  
1.  <span data-ttu-id="c8735-226">Выполните инструкцию RESTORE DATABASE для восстановления резервной копии файлов и файловых групп, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="c8735-226">Execute the RESTORE DATABASE statement to restore the file and filegroup backup, specifying:</span></span>  
  
    -   <span data-ttu-id="c8735-227">Имя базы данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="c8735-227">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="c8735-228">Устройство резервного копирования, откуда будет восстановлена полная резервная копия.</span><span class="sxs-lookup"><span data-stu-id="c8735-228">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="c8735-229">предложение FILE для каждого восстанавливаемого файла;</span><span class="sxs-lookup"><span data-stu-id="c8735-229">The FILE clause for each file to restore.</span></span>  
  
    -   <span data-ttu-id="c8735-230">предложение FILEGROUP для каждой восстанавливаемой файловой группы;</span><span class="sxs-lookup"><span data-stu-id="c8735-230">The FILEGROUP clause for each filegroup to restore.</span></span>  
  
    -   <span data-ttu-id="c8735-231">Предложение NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c8735-231">The NORECOVERY clause.</span></span> <span data-ttu-id="c8735-232">(если файлы не изменялись со времени создания резервной копии, укажите предложение RECOVERY).</span><span class="sxs-lookup"><span data-stu-id="c8735-232">If the files have not been modified after the backup was created, specify the RECOVERY clause.</span></span>  
  
2.  <span data-ttu-id="c8735-233">Если файлы были изменены после создания резервной копии, выполните инструкцию RESTORE LOG для применения резервной копии журнала транзакций, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="c8735-233">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="c8735-234">Имя базы данных, к которой будет применен журнал транзакций.</span><span class="sxs-lookup"><span data-stu-id="c8735-234">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="c8735-235">Устройство резервного копирования, с которого будет восстановлена резервная копия журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="c8735-235">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="c8735-236">Предложение NORECOVERY, если существует другая резервная копия журналов транзакций для применения после текущего; в противном случае укажите предложение RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c8735-236">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="c8735-237">В случае применения резервных копий журналов транзакций они должны охватывать время резервного копирования файлов и их групп вплоть до конца журналов (если только не восстанавливаются ВСЕ файлы базы данных).</span><span class="sxs-lookup"><span data-stu-id="c8735-237">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up until the end of log (unless ALL database files are restored).</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c8735-238">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c8735-238">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c8735-239">В этом примере восстанавливаются файлы и файловые группы базы данных `MyDatabase` .</span><span class="sxs-lookup"><span data-stu-id="c8735-239">This example restores the files and filegroups for the `MyDatabase` database.</span></span> <span data-ttu-id="c8735-240">При восстановлении базы данных до текущего момента будут применены два журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="c8735-240">To restore the database to the current time, two transaction logs are applied.</span></span>  
  
```sql  
USE master;  
GO  
-- Restore the files and filesgroups for MyDatabase.  
RESTORE DATABASE MyDatabase  
   FILE = 'MyDatabase_data_1',  
   FILEGROUP = 'new_customers',  
   FILE = 'MyDatabase_data_2',  
   FILEGROUP = 'first_qtr_sales'  
   FROM MyDatabase_1  
   WITH NORECOVERY;  
GO  
-- Apply the first transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log1  
   WITH NORECOVERY;  
GO  
-- Apply the last transaction log backup.  
RESTORE LOG MyDatabase  
   FROM MyDatabase_log2  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8735-241">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8735-241">See Also</span></span>  
 <span data-ttu-id="c8735-242">[Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="c8735-242">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="c8735-243">[Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8735-243">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="c8735-244">[Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8735-244">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="c8735-245">[Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8735-245">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="c8735-246">[Восстановление резервной копии журнала транзакций (SQL Server)](restore-a-transaction-log-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8735-246">[Restore a Transaction Log Backup &#40;SQL Server&#41;](restore-a-transaction-log-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="c8735-247">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c8735-247">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
