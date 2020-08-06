---
title: Восстановление резервной копии с устройства (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring databases [SQL Server], device restores
- backup devices [SQL Server], restoring from
- database restores [SQL Server], device restores
- devices [SQL Server]
ms.assetid: 6e139de7-7de2-4d18-9df0-beac31ba7ff1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50d7f7b8e255aea470a1065df669c0cc3169a8dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730758"
---
# <a name="restore-a-backup-from-a-device-sql-server"></a><span data-ttu-id="2d8ed-102">Восстановление резервной копии с устройства (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2d8ed-102">Restore a Backup from a Device (SQL Server)</span></span>
  <span data-ttu-id="2d8ed-103">В этом разделе описано, как восстановить журнал транзакций с устройства в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d8ed-103">This topic describes how to restore a backup from a device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d8ed-104">Сведения о SQL Server резервного копирования в службу хранилища BLOB-объектов Azure см. в статье [SQL Server резервное копирование и восстановление с помощью службы хранилища BLOB-объектов Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="2d8ed-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="2d8ed-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2d8ed-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2d8ed-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2d8ed-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d8ed-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2d8ed-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d8ed-108">**Восстановление резервной копии с устройства с помощью:**</span><span class="sxs-lookup"><span data-stu-id="2d8ed-108">**To restore a backup from a device, using:**</span></span>  
  
     [<span data-ttu-id="2d8ed-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d8ed-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2d8ed-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d8ed-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d8ed-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2d8ed-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d8ed-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="2d8ed-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d8ed-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="2d8ed-113">Permissions</span></span>  
 <span data-ttu-id="2d8ed-114">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-114">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="2d8ed-115">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="2d8ed-115">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="2d8ed-116">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-116">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="2d8ed-117">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-117">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2d8ed-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d8ed-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="2d8ed-119">Восстановление резервной копии с устройства</span><span class="sxs-lookup"><span data-stu-id="2d8ed-119">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="2d8ed-120">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2d8ed-121">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="2d8ed-122">Щелкните правой кнопкой мыши базу данных, укажите на пункт **Задачи**и щелкните **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-122">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="2d8ed-123">Выберите нужный тип операции восстановления (**База данных**, **Файлы и файловые группы**или **Журнал транзакций**).</span><span class="sxs-lookup"><span data-stu-id="2d8ed-123">Click the type of restore operation you want (**Database**, **Files and Filegroups**, or **Transaction Log**).</span></span> <span data-ttu-id="2d8ed-124">Откроется соответствующее диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-124">This opens the corresponding restore dialog box.</span></span>  
  
5.  <span data-ttu-id="2d8ed-125">На странице **Общие** в разделе **Источник для восстановления** выберите **С устройства**.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-125">On the **General** page, in the **Restore source** section, click **From device**.</span></span>  
  
6.  <span data-ttu-id="2d8ed-126">В текстовом поле **С устройства** нажмите кнопку обзора. Откроется диалоговое окно **Указание резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="2d8ed-126">Click the browse button for the **From device** text box, which opens the **Specify Backup** dialog box.</span></span>  
  
7.  <span data-ttu-id="2d8ed-127">В текстовом поле **Носитель резервной копии** выберите **Устройство резервного копирования**и нажмите кнопку **Добавить** . Откроется текстовое поле **Выбор устройства резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="2d8ed-127">In the **Backup media** text box, select **Backup Device**, and click the **Add** button to open the **Select Backup Device** dialog box.</span></span>  
  
8.  <span data-ttu-id="2d8ed-128">В текстовом поле **Устройство резервного копирования** выберите устройство для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-128">In the **Backup device** text box, select the device you want to use for the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2d8ed-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d8ed-129">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="2d8ed-130">Восстановление резервной копии с устройства</span><span class="sxs-lookup"><span data-stu-id="2d8ed-130">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="2d8ed-131">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d8ed-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2d8ed-132">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2d8ed-133">В инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) укажите логическое или физическое устройство резервного копирования, которое будет использоваться для создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-133">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify a logical or physical backup device to use for the backup operation.</span></span> <span data-ttu-id="2d8ed-134">В этом примере показано восстановление из файла на диске, имеющего физическое имя `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-134">This example restores from a disk file that has the physical name `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak' ;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d8ed-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d8ed-135">See Also</span></span>  
 <span data-ttu-id="2d8ed-136">[Инструкция RESTORE FILELISTONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="2d8ed-137">[RESTORE HEADERONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="2d8ed-138">[RESTORE LABELONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="2d8ed-139">[RESTORE VERIFYONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="2d8ed-140">[Восстановление резервной копии базы данных в простой модели восстановления (Transact-SQL)](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-140">[Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span></span>  
 <span data-ttu-id="2d8ed-141">[Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-141">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="2d8ed-142">[Восстановление разностной резервной копии базы данных (SQL Server)](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-142">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="2d8ed-143">[Восстановление базы данных в новое место (SQL Server)](restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-143">[Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="2d8ed-144">[Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-144">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="2d8ed-145">[Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2d8ed-145">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="2d8ed-146">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2d8ed-146">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
