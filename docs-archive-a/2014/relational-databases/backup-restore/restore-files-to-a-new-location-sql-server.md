---
title: Восстановление файлов в новое место (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring files [SQL Server], how-to topics
- restoring databases [SQL Server], moving
- restoring files [SQL Server], steps
- file restores [SQL Server], how-to topics
- filegroups [SQL Server], restoring
- restoring filegroups [SQL Server]
ms.assetid: b4f4791d-646e-4632-9980-baae9cb1aade
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a8336e5d186fb72df4e0a17fdd9affccab4ee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731738"
---
# <a name="restore-files-to-a-new-location-sql-server"></a><span data-ttu-id="a67cd-102">Восстановление файлов в новое место (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a67cd-102">Restore Files to a New Location (SQL Server)</span></span>
  <span data-ttu-id="a67cd-103">В этом разделе описано, как восстановить файлы в новом расположении в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a67cd-103">This topic describes how to restore files to a new location in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a67cd-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a67cd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a67cd-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a67cd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a67cd-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a67cd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a67cd-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a67cd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a67cd-108">**Восстановление файлов в новом расположении с помощью:**</span><span class="sxs-lookup"><span data-stu-id="a67cd-108">**To restore files to a new location, using:**</span></span>  
  
     [<span data-ttu-id="a67cd-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a67cd-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a67cd-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a67cd-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a67cd-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a67cd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a67cd-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a67cd-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a67cd-113">Системный администратор, восстанавливающий файлы, должен быть единственным лицом, использующим восстанавливаемую базу данных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a67cd-113">The system administrator restoring the files must be the only person currently using the database to be restored.</span></span>  
  
-   <span data-ttu-id="a67cd-114">Инструкция RESTORE недопустима в явной или неявной транзакции.</span><span class="sxs-lookup"><span data-stu-id="a67cd-114">RESTORE is not allowed in an explicit or implicit transaction.</span></span>  
  
-   <span data-ttu-id="a67cd-115">Перед началом восстановления файлов по модели полного восстановления или модели восстановления с неполным протоколированием необходимо выполнить резервное копирование активного журнала транзакций (который называется заключительным фрагментом журнала).</span><span class="sxs-lookup"><span data-stu-id="a67cd-115">Under the full or bulk-logged recovery model, before you can restore files, you must back up the active transaction log (known as the tail of the log).</span></span> <span data-ttu-id="a67cd-116">Дополнительные сведения см. в статье [Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="a67cd-116">For more information, see [Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="a67cd-117">Чтобы восстановить зашифрованную базу данных, необходимо иметь доступ к сертификату или асимметричному ключу, который использовался для шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="a67cd-117">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="a67cd-118">Без сертификата или асимметричного ключа восстановить базу данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="a67cd-118">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="a67cd-119">Поэтому сертификат, используемый для шифрования ключа шифрования базы данных, должен храниться в течение всего времени, пока есть необходимость в резервной копии.</span><span class="sxs-lookup"><span data-stu-id="a67cd-119">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="a67cd-120">Дополнительные сведения см. в статье [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a67cd-120">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a67cd-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="a67cd-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a67cd-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="a67cd-122">Permissions</span></span>  
 <span data-ttu-id="a67cd-123">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="a67cd-123">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="a67cd-124">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="a67cd-124">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="a67cd-125">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="a67cd-125">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="a67cd-126">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="a67cd-126">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a67cd-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a67cd-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="a67cd-128">Восстановление файлов и групп файлов в новое место</span><span class="sxs-lookup"><span data-stu-id="a67cd-128">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="a67cd-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], разверните его, а затем разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-129">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="a67cd-130">Щелкните правой кнопкой мыши нужную базу данных, наведите указатель на пункт **Задачи**, а затем выберите пункты **Восстановить**и **Файлы и файловые группы**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-130">Right-click the database that you want, point to **Tasks**, point to **Restore**, and then click **Files and Filegroups**.</span></span>  
  
3.  <span data-ttu-id="a67cd-131">На странице **Общие** в списке **В базу данных** введите имя восстанавливаемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="a67cd-131">On the **General** page, in the **To database** list box, enter the database to restore.</span></span> <span data-ttu-id="a67cd-132">Можно ввести новую базу данных или выбрать уже существующую из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a67cd-132">You can enter a new database or choose an existing database from the drop-down list.</span></span> <span data-ttu-id="a67cd-133">Список включает все базы данных на сервере кроме системных баз данных **master** и **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-133">The list includes all databases on the server, excluding the system databases **master** and **tempdb**.</span></span>  
  
4.  <span data-ttu-id="a67cd-134">Чтобы указать источник и расположение восстанавливаемых резервных наборов данных, выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="a67cd-134">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="a67cd-135">**Из базы данных**</span><span class="sxs-lookup"><span data-stu-id="a67cd-135">**From database**</span></span>  
  
         <span data-ttu-id="a67cd-136">Введите имя базы данных в списке.</span><span class="sxs-lookup"><span data-stu-id="a67cd-136">Enter a database name in the list box.</span></span> <span data-ttu-id="a67cd-137">Данный список содержит только базы данных, резервное копирование которых было выполнено в соответствии с журналом резервного копирования **msdb** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-137">This list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="a67cd-138">**С устройства**</span><span class="sxs-lookup"><span data-stu-id="a67cd-138">**From device**</span></span>  
  
         <span data-ttu-id="a67cd-139">Нажмите кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="a67cd-139">Click the browse button.</span></span> <span data-ttu-id="a67cd-140">В диалоговом окне **Указание устройств резервного копирования** выберите один из перечисленных типов устройств в списке **Тип носителя резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-140">In the **Specify backup devices** dialog box, select one of the listed device types in the **Backup media type** list box.</span></span> <span data-ttu-id="a67cd-141">Чтобы выбрать одно или несколько устройств в списке **Носитель резервной копии** , нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-141">To select one or more devices for the **Backup media** list box, click **Add**.</span></span>  
  
         <span data-ttu-id="a67cd-142">После добавления нужных устройств в списке **Носитель резервной копии** нажмите кнопку **ОК** для возвращения на страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-142">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
5.  <span data-ttu-id="a67cd-143">В сетке **Выберите резервные наборы данных для восстановления** выберите нужные резервные наборы.</span><span class="sxs-lookup"><span data-stu-id="a67cd-143">In the **Select the backup sets to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="a67cd-144">В этой сетке отображаются резервные копии, доступные в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="a67cd-144">This grid displays the backups available for the specified location.</span></span> <span data-ttu-id="a67cd-145">По умолчанию предлагается план восстановления.</span><span class="sxs-lookup"><span data-stu-id="a67cd-145">By default, a recovery plan is suggested.</span></span> <span data-ttu-id="a67cd-146">Чтобы переопределить предложенный план восстановления, можно изменить выбранные элементы в сетке.</span><span class="sxs-lookup"><span data-stu-id="a67cd-146">To override the suggested recovery plan, you can change the selections in the grid.</span></span> <span data-ttu-id="a67cd-147">Если выбор каких-то резервных копий отменяется, то автоматически отменяется и выбор зависящих от них резервных копий.</span><span class="sxs-lookup"><span data-stu-id="a67cd-147">Any backups that depend on a deselected backup are deselected automatically.</span></span>  
  
    |<span data-ttu-id="a67cd-148">Заголовок столбца</span><span class="sxs-lookup"><span data-stu-id="a67cd-148">Column head</span></span>|<span data-ttu-id="a67cd-149">Значения</span><span class="sxs-lookup"><span data-stu-id="a67cd-149">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="a67cd-150">**Восстановление**</span><span class="sxs-lookup"><span data-stu-id="a67cd-150">**Restore**</span></span>|<span data-ttu-id="a67cd-151">Установленные флажки обозначают резервные наборы данных, отмеченные для восстановления.</span><span class="sxs-lookup"><span data-stu-id="a67cd-151">The selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="a67cd-152">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a67cd-152">**Name**</span></span>|<span data-ttu-id="a67cd-153">Имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="a67cd-153">The name of the backup set.</span></span>|  
    |<span data-ttu-id="a67cd-154">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="a67cd-154">**File Type**</span></span>|<span data-ttu-id="a67cd-155">Задает тип данных в резервной копии: **Данные**, **Журнал** или **Данные Filestream**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-155">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="a67cd-156">Данные, содержащиеся в таблицах, хранятся в файлах типа **Данные** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-156">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="a67cd-157">Данные журнала транзакций хранятся в файлах типа **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-157">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="a67cd-158">Данные больших двоичных объектов (BLOB), которые хранятся в файловой системе, находятся в файлах типа **Данные Filestream** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-158">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="a67cd-159">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a67cd-159">**Type**</span></span>|<span data-ttu-id="a67cd-160">Тип выполняемого резервного копирования: **Полное**, **Разностное**или **Журнал транзакций**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-160">The type of backup performed: **Full**, **Differential**, or **Transaction Log**.</span></span>|  
    |<span data-ttu-id="a67cd-161">**Server**</span><span class="sxs-lookup"><span data-stu-id="a67cd-161">**Server**</span></span>|<span data-ttu-id="a67cd-162">Имя экземпляра ядра СУБД, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a67cd-162">The name of the Database-Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="a67cd-163">**Логическое имя файла**</span><span class="sxs-lookup"><span data-stu-id="a67cd-163">**File Logical Name**</span></span>|<span data-ttu-id="a67cd-164">Логическое имя файла.</span><span class="sxs-lookup"><span data-stu-id="a67cd-164">The logical name of the file.</span></span>|  
    |<span data-ttu-id="a67cd-165">**База данных**</span><span class="sxs-lookup"><span data-stu-id="a67cd-165">**Database**</span></span>|<span data-ttu-id="a67cd-166">Имя базы данных, участвовавшей в операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a67cd-166">The name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="a67cd-167">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="a67cd-167">**Start Date**</span></span>|<span data-ttu-id="a67cd-168">Дата и время начала операции резервного копирования, указанные в региональных настройках клиента.</span><span class="sxs-lookup"><span data-stu-id="a67cd-168">The date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="a67cd-169">**Дата завершения**</span><span class="sxs-lookup"><span data-stu-id="a67cd-169">**Finish Date**</span></span>|<span data-ttu-id="a67cd-170">Дата и время завершения операции резервного копирования, указанные в формате, соответствующем региональным настройкам клиента.</span><span class="sxs-lookup"><span data-stu-id="a67cd-170">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="a67cd-171">**Размер**</span><span class="sxs-lookup"><span data-stu-id="a67cd-171">**Size**</span></span>|<span data-ttu-id="a67cd-172">Размер резервного набора данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="a67cd-172">The size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="a67cd-173">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="a67cd-173">**User Name**</span></span>|<span data-ttu-id="a67cd-174">Имя пользователя, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a67cd-174">The name of the user who performed the backup operation.</span></span>|  
  
6.  <span data-ttu-id="a67cd-175">На панели **Выбор страницы** щелкните **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-175">In the **Select a page** pane, click the **Options** page.</span></span>  
  
7.  <span data-ttu-id="a67cd-176">В сетке **Восстановить файлы базы данных как** укажите новое расположение для перемещаемых файлов.</span><span class="sxs-lookup"><span data-stu-id="a67cd-176">In the **Restore database files as** grid, specify a new location for the file or files that you want to move.</span></span>  
  
    |<span data-ttu-id="a67cd-177">Заголовок столбца</span><span class="sxs-lookup"><span data-stu-id="a67cd-177">Column head</span></span>|<span data-ttu-id="a67cd-178">Значения</span><span class="sxs-lookup"><span data-stu-id="a67cd-178">Values</span></span>|  
    |-----------------|------------|  
    |<span data-ttu-id="a67cd-179">**Имя исходного файла**</span><span class="sxs-lookup"><span data-stu-id="a67cd-179">**Original File Name**</span></span>|<span data-ttu-id="a67cd-180">Полный путь исходного файла резервной копии.</span><span class="sxs-lookup"><span data-stu-id="a67cd-180">The full path of a source backup file.</span></span>|  
    |<span data-ttu-id="a67cd-181">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="a67cd-181">**File Type**</span></span>|<span data-ttu-id="a67cd-182">Задает тип данных в резервной копии: **Данные**, **Журнал** или **Данные Filestream**.</span><span class="sxs-lookup"><span data-stu-id="a67cd-182">Specifies the type of data in the backup: **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="a67cd-183">Данные, содержащиеся в таблицах, хранятся в файлах типа **Данные** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-183">Data that is contained in tables is in **Data** files.</span></span> <span data-ttu-id="a67cd-184">Данные журнала транзакций хранятся в файлах типа **Журнал** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-184">Transaction log data is in **Log** files.</span></span> <span data-ttu-id="a67cd-185">Данные больших двоичных объектов (BLOB), которые хранятся в файловой системе, находятся в файлах типа **Данные Filestream** .</span><span class="sxs-lookup"><span data-stu-id="a67cd-185">Binary large object (BLOB) data that is stored on the file system is in **Filestream Data** files.</span></span>|  
    |<span data-ttu-id="a67cd-186">**Восстановить как**</span><span class="sxs-lookup"><span data-stu-id="a67cd-186">**Restore As**</span></span>|<span data-ttu-id="a67cd-187">Полный путь к файлу базы данных, который нужно восстановить.</span><span class="sxs-lookup"><span data-stu-id="a67cd-187">The full path of the database file to be restored.</span></span> <span data-ttu-id="a67cd-188">Чтобы указать новый восстанавливаемый файл, щелкните текстовое поле и измените предложенные путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="a67cd-188">To specify a new restore file, click the text box and edit the suggested path and file name.</span></span> <span data-ttu-id="a67cd-189">Изменение пути или имени файла в столбце **Восстановить как** равнозначно использованию параметра MOVE в инструкции RESTORE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a67cd-189">Changing the path or file name in the **Restore As** column is equivalent to using the MOVE option in a [!INCLUDE[tsql](../../includes/tsql-md.md)] RESTORE statement.</span></span>|  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a67cd-190">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a67cd-190">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-files-to-a-new-location"></a><span data-ttu-id="a67cd-191">Восстановление файлов и групп файлов в новое место</span><span class="sxs-lookup"><span data-stu-id="a67cd-191">To restore files to a new location</span></span>  
  
1.  <span data-ttu-id="a67cd-192">При необходимости выполните инструкцию RESTORE FILELISTONLY, чтобы выяснить число и имена файлов в полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="a67cd-192">Optionally, execute the RESTORE FILELISTONLY statement to determine the number and names of the files in the full database backup.</span></span>  
  
2.  <span data-ttu-id="a67cd-193">Для восстановления полной резервной копии базы данных выполните инструкцию RESTORE DATABASE, указав:</span><span class="sxs-lookup"><span data-stu-id="a67cd-193">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="a67cd-194">Имя базы данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="a67cd-194">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="a67cd-195">Устройство резервного копирования, откуда будет восстановлена полная резервная копия.</span><span class="sxs-lookup"><span data-stu-id="a67cd-195">The backup device from where the full database backup will be restored.</span></span>  
  
    -   <span data-ttu-id="a67cd-196">Предложение MOVE для каждого восстанавливаемого в новое место файла.</span><span class="sxs-lookup"><span data-stu-id="a67cd-196">The MOVE clause for each file to restore to a new location.</span></span>  
  
    -   <span data-ttu-id="a67cd-197">Предложение NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="a67cd-197">The NORECOVERY clause.</span></span>  
  
3.  <span data-ttu-id="a67cd-198">Если файлы были изменены после создания резервной копии, выполните инструкцию RESTORE LOG для применения резервной копии журнала транзакций, указав следующее:</span><span class="sxs-lookup"><span data-stu-id="a67cd-198">If the files have been modified after the file backup was created, execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="a67cd-199">Имя базы данных, к которой будет применен журнал транзакций.</span><span class="sxs-lookup"><span data-stu-id="a67cd-199">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="a67cd-200">Устройство резервного копирования, с которого будет восстановлена резервная копия журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="a67cd-200">The backup device from where the transaction log backup will be restored.</span></span>  
  
    -   <span data-ttu-id="a67cd-201">Предложение NORECOVERY, если существует другая резервная копия журналов транзакций для применения после текущего; в противном случае укажите предложение RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="a67cd-201">The NORECOVERY clause if you have another transaction log backup to apply after the current one; otherwise, specify the RECOVERY clause.</span></span>  
  
         <span data-ttu-id="a67cd-202">Резервные копии журналов транзакций, в случае их использования, должны включать в себя промежуток времени, в течение которого создавались резервные копии файлов и файловых групп.</span><span class="sxs-lookup"><span data-stu-id="a67cd-202">The transaction log backups, if applied, must cover the time when the files and filegroups were backed up.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="a67cd-203">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a67cd-203">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="a67cd-204">В этом примере восстанавливаются два файла базы данных `MyNwind` , первоначально находившиеся на диске C, в новое место на диске D. Также будут применены два журнала транзакций для восстановления базы данных на текущий момент времени.</span><span class="sxs-lookup"><span data-stu-id="a67cd-204">This example restores two of the files for the `MyNwind` database that were originally located on Drive C to new locations on Drive D. Two transaction logs will also be applied to restore the database to the current time.</span></span> <span data-ttu-id="a67cd-205">Количество восстанавливаемых файлов базы данных, а также их логические и физические имена можно определить с помощью инструкции `RESTORE FILELISTONLY` .</span><span class="sxs-lookup"><span data-stu-id="a67cd-205">The `RESTORE FILELISTONLY` statement is used to determine the number and logical and physical names of the files in the database being restored.</span></span>  
  
```sql  
USE master;  
GO  
-- First determine the number and names of the files in the backup.  
RESTORE FILELISTONLY  
   FROM MyNwind_1;  
-- Restore the files for MyNwind.  
RESTORE DATABASE MyNwind  
   FROM MyNwind_1  
   WITH NORECOVERY,  
   MOVE 'MyNwind_data_1' TO 'D:\MyData\MyNwind_data_1.mdf',   
   MOVE 'MyNwind_data_2' TO 'D:\MyData\MyNwind_data_2.ndf';  
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
  
## <a name="see-also"></a><span data-ttu-id="a67cd-206">См. также:</span><span class="sxs-lookup"><span data-stu-id="a67cd-206">See Also</span></span>  
 <span data-ttu-id="a67cd-207">[Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="a67cd-207">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="a67cd-208">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a67cd-208">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="a67cd-209">[Копирование баз данных путем создания и восстановления резервных копий](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="a67cd-209">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="a67cd-210">Восстановление файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a67cd-210">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](restore-files-and-filegroups-sql-server.md)  
  
  
