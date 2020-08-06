---
title: Укажите, будет ли операция резервного копирования или восстановления продолжаться или остановлена после возникновения ошибки (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], backups
- backing up databases [SQL Server], errors
- backups [SQL Server], errors
- database backups [SQL Server], errors
ms.assetid: 042be17a-b9b0-4629-b6bb-b87a8bc6c316
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 87cccec6f7eea18f2750d3b0be81b577b0eb170a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667738"
---
# <a name="specify-whether-a-backup-or-restore-operation-continues-or-stops-after-encountering-an-error-sql-server"></a><span data-ttu-id="9b12e-102">Определение, продолжает ли операция резервного копирования или восстановления работу после возникновения ошибки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b12e-102">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error (SQL Server)</span></span>
  <span data-ttu-id="9b12e-103">В этом разделе описывается, как определить, будут ли операции резервного копирования и восстановления продолжать работу или останавливаться при ошибке в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b12e-103">This topic describes how to specify whether a backup or restore operation continues or stops after encountering an error in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9b12e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="9b12e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9b12e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="9b12e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9b12e-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9b12e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9b12e-107">**Определение, продолжает ли операция резервного копирования или восстановления работу после возникновения ошибки, с помощью следующих средств.**</span><span class="sxs-lookup"><span data-stu-id="9b12e-107">**To specify whether a backup or restore operation continues after encountering an error, using:**</span></span>  
  
     [<span data-ttu-id="9b12e-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b12e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9b12e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b12e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9b12e-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9b12e-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b12e-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="9b12e-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9b12e-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="9b12e-112">Permissions</span></span>  
 <span data-ttu-id="9b12e-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="9b12e-113">BACKUP</span></span>  
 <span data-ttu-id="9b12e-114">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="9b12e-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="9b12e-115">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="9b12e-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9b12e-116">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="9b12e-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="9b12e-117">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="9b12e-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="9b12e-118">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="9b12e-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="9b12e-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="9b12e-119">RESTORE</span></span>  
 <span data-ttu-id="9b12e-120">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="9b12e-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="9b12e-121">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="9b12e-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="9b12e-122">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="9b12e-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="9b12e-123">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9b12e-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9b12e-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b12e-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-whether-backup-continues-or-stops-after-an-error-is-encountered"></a><span data-ttu-id="9b12e-125">Определение, продолжается или останавливается резервное копирование при возникновении ошибки</span><span class="sxs-lookup"><span data-stu-id="9b12e-125">To specify whether backup continues or stops after an error is encountered</span></span>  
  
1.  <span data-ttu-id="9b12e-126">Выполните следующие шаги, чтобы [создать резервную копию базы данных](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b12e-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="9b12e-127">На странице **Параметры** в разделе **Надежность** выберите параметр **Вычислять контрольную сумму перед записью на носитель** и **Продолжить при возникновении ошибки**.</span><span class="sxs-lookup"><span data-stu-id="9b12e-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media** and **Continue on error**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9b12e-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b12e-128">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-whether-a-backup-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="9b12e-129">Определение, продолжает ли операция резервного копирования работу или останавливается после возникновения ошибки</span><span class="sxs-lookup"><span data-stu-id="9b12e-129">To specify whether a backup operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="9b12e-130">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b12e-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b12e-131">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="9b12e-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b12e-132">В инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) задайте параметр CONTINUE_AFTER ERROR для продолжения или STOP_ON_ERROR для остановки.</span><span class="sxs-lookup"><span data-stu-id="9b12e-132">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="9b12e-133">По умолчанию в случае ошибки операция останавливается.</span><span class="sxs-lookup"><span data-stu-id="9b12e-133">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="9b12e-134">В этом примере операция резервного копирования настраивается на продолжение работы в случае ошибки.</span><span class="sxs-lookup"><span data-stu-id="9b12e-134">This example instructs the backup operation to continue despite encountering an error.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
#### <a name="to-specify-whether-a-restore-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="9b12e-135">Определение, продолжает ли операция восстановления работу или останавливается после возникновения ошибки</span><span class="sxs-lookup"><span data-stu-id="9b12e-135">To specify whether a restore operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="9b12e-136">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b12e-136">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b12e-137">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="9b12e-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9b12e-138">В инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) укажите параметр CONTINUE_AFTER ERROR для продолжения или STOP_ON_ERROR для остановки.</span><span class="sxs-lookup"><span data-stu-id="9b12e-138">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="9b12e-139">По умолчанию в случае ошибки операция останавливается.</span><span class="sxs-lookup"><span data-stu-id="9b12e-139">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="9b12e-140">В этом примере операция восстановления настраивается на продолжение работы в случае ошибки.</span><span class="sxs-lookup"><span data-stu-id="9b12e-140">This example instructs the restore operation to continue despite encountering an error.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'   
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b12e-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b12e-141">See Also</span></span>  
 <span data-ttu-id="9b12e-142">[Инструкция RESTORE FILELISTONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b12e-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="9b12e-143">[RESTORE HEADERONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b12e-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="9b12e-144">[RESTORE LABELONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b12e-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="9b12e-145">[RESTORE VERIFYONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b12e-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="9b12e-146">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b12e-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9b12e-147">[backupset (Transact-SQL)](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b12e-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="9b12e-148">[Аргументы инструкции RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b12e-148">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="9b12e-149">[Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b12e-149">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="9b12e-150">Включение или отключение вычисления контрольных сумм резервных копий во время резервного копирования или восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9b12e-150">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
  
