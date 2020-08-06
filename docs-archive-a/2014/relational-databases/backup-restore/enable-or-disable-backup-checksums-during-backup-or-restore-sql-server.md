---
title: Включение или отключение вычисления контрольных сумм резервных копий во время архивации или восстановления (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup checksums [SQL Server]
- disabling checksums
- checksums [SQL Server]
ms.assetid: 6786bd1e-ad97-430a-8dfb-d4ba952d6c4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a239dcdfca689be8555117104264d66a2ac037f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751231"
---
# <a name="enable-or-disable-backup-checksums-during-backup-or-restore-sql-server"></a><span data-ttu-id="7a5fb-102">Включение или отключение вычисления контрольных сумм резервных копий во время резервного копирования или восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a5fb-102">Enable or Disable Backup Checksums During Backup or Restore (SQL Server)</span></span>
  <span data-ttu-id="7a5fb-103">В этом разделе описано, как включить или отключить контрольные суммы резервных копий при резервном копировании или восстановлении базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a5fb-103">This topic describes how to enable or disable backup checksums when you are backing up or restoring a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7a5fb-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="7a5fb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a5fb-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="7a5fb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a5fb-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7a5fb-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a5fb-107">**Включение или отключение расчета контрольных сумм резервных копий**</span><span class="sxs-lookup"><span data-stu-id="7a5fb-107">**To enable or disable backup checksums, using:**</span></span>  
  
     [<span data-ttu-id="7a5fb-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a5fb-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a5fb-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a5fb-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a5fb-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="7a5fb-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a5fb-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="7a5fb-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a5fb-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="7a5fb-112">Permissions</span></span>  
 <span data-ttu-id="7a5fb-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="7a5fb-113">BACKUP</span></span>  
 <span data-ttu-id="7a5fb-114">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="7a5fb-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="7a5fb-115">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7a5fb-116">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="7a5fb-117">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="7a5fb-118">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="7a5fb-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="7a5fb-119">RESTORE</span></span>  
 <span data-ttu-id="7a5fb-120">Если восстанавливаемая база данных не существуют, для выполнения инструкции RESTORE у пользователя должны быть разрешения CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="7a5fb-121">Если база данных существует, разрешения на выполнение инструкции RESTORE по умолчанию предоставлены членам предопределенных ролей сервера **sysadmin** и **dbcreator** , а также владельцу базы данных (**dbo**) (для параметра FROM DATABASE_SNAPSHOT база данных всегда существует).</span><span class="sxs-lookup"><span data-stu-id="7a5fb-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="7a5fb-122">Разрешения на выполнение инструкции RESTORE даются ролям, в которых данные о членстве всегда доступны серверу.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="7a5fb-123">Так как членство в предопределенной роли базы данных может быть проверено только тогда, когда база данных доступна и не повреждена, что не всегда имеет место при выполнении инструкции RESTORE, члены предопределенной роли базы данных **db_owner** не имеют разрешений RESTORE.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a5fb-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a5fb-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-or-disable-checksums-during-a-backup-operation"></a><span data-ttu-id="7a5fb-125">Включение или отключение вычисления контрольных сумм во время создания резервной копии</span><span class="sxs-lookup"><span data-stu-id="7a5fb-125">To enable or disable checksums during a backup operation</span></span>  
  
1.  <span data-ttu-id="7a5fb-126">Выполните следующие шаги, чтобы [создать резервную копию базы данных](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a5fb-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="7a5fb-127">На странице **Параметры** в разделе **Надежность** выберите параметр **Вычислять контрольную сумму перед записью на носитель**.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a5fb-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a5fb-128">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-backup-operation"></a><span data-ttu-id="7a5fb-129">Включение или отключение вычисления контрольных сумм для операции создания резервной копии</span><span class="sxs-lookup"><span data-stu-id="7a5fb-129">To enable or disable backup checksum for a backup operation</span></span>  
  
1.  <span data-ttu-id="7a5fb-130">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a5fb-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a5fb-131">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a5fb-132">Чтобы включить контрольные суммы резервных копий в инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) , укажите параметр WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-132">To enable backup checksums in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="7a5fb-133">Чтобы отключить контрольные суммы резервных копий, укажите параметр WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-133">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="7a5fb-134">Это поведение по умолчанию для всех, за исключением сжатых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-134">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="7a5fb-135">В следующем примере указывается, что контрольные суммы будут вычисляться.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-135">The following example specifies that checksums be performed.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-restore-operation"></a><span data-ttu-id="7a5fb-136">Включение или отключение вычисления контрольных сумм для операции восстановления из резервной копии</span><span class="sxs-lookup"><span data-stu-id="7a5fb-136">To enable or disable backup checksum for a restore operation</span></span>  
  
1.  <span data-ttu-id="7a5fb-137">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a5fb-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a5fb-138">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a5fb-139">Чтобы включить контрольные суммы резервных копий в инструкции [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , укажите параметр WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-139">To enable backup checksums in a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="7a5fb-140">Это поведение по умолчанию для сжатых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-140">This is the default behavior for a compressed backup.</span></span> <span data-ttu-id="7a5fb-141">Чтобы отключить контрольные суммы резервных копий, укажите параметр WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-141">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="7a5fb-142">Это поведение по умолчанию для всех, за исключением сжатых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-142">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="7a5fb-143">В следующем примере указывается, что контрольные суммы резервных копий будут вычисляться.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-143">The following example specifies that backup checksums be performed.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
> [!WARNING]  
>  <span data-ttu-id="7a5fb-144">Если явно запрашивается CHECKSUM для операции восстановления и если резервная копия содержит контрольные суммы, то проверяются контрольные суммы и резервной копии, и страниц, как в случае по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-144">If you explicitly request CHECKSUM for a restore operation and if the backup contains backup checksums, backup checksums and page checksums are both verified, as in the default case.</span></span> <span data-ttu-id="7a5fb-145">Однако если в резервном наборе данных нет контрольных сумм, такая операция восстановления завершается аварийно с сообщением об отсутствии контрольных сумм.</span><span class="sxs-lookup"><span data-stu-id="7a5fb-145">However, if the backup set lacks backup checksums, the restore operation fails with a message indicating that checksums are not present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5fb-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a5fb-146">See Also</span></span>  
 <span data-ttu-id="7a5fb-147">[Инструкция RESTORE FILELISTONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="7a5fb-148">[RESTORE HEADERONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="7a5fb-149">[RESTORE LABELONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="7a5fb-150">[RESTORE VERIFYONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="7a5fb-151">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="7a5fb-152">[backupset (Transact-SQL)](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="7a5fb-153">[Аргументы инструкции RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-153">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="7a5fb-154">[Возможные ошибки носителей во время резервного копирования и восстановления (SQL Server)](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a5fb-154">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="7a5fb-155">Определение, продолжает ли операция резервного копирования или восстановления работу после возникновения ошибки (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a5fb-155">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
  
