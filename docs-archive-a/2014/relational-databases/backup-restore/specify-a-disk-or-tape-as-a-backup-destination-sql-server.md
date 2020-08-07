---
title: Указание диска или ленты в качестве места назначения архивации (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
- backups [SQL Server], creating
- tape backup devices, backing up
ms.assetid: e391f452-ed8c-4b40-b846-ac3881271b94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a0f8ec5d9741e42f3b7d8eda8ebdba23622982d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731733"
---
# <a name="specify-a-disk-or-tape-as-a-backup-destination-sql-server"></a><span data-ttu-id="5eeb0-102">Указание в качестве назначения резервного копирования диска или ленты (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5eeb0-102">Specify a Disk or Tape As a Backup Destination (SQL Server)</span></span>
  <span data-ttu-id="5eeb0-103">В этом разделе описывается, как указать диск или ленту для резервного копирования в среде [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eeb0-103">This topic describes how to specify a disk or tape as a backup destination in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5eeb0-104">Поддержка резервного копирования на ленточные устройства будет исключена в будущей версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="5eeb0-105">Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="5eeb0-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5eeb0-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5eeb0-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5eeb0-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5eeb0-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5eeb0-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5eeb0-109">**Указание в качестве назначения резервного копирования диска или ленты с помощью.**</span><span class="sxs-lookup"><span data-stu-id="5eeb0-109">**To specify a disk or tape as a backup destination, using:**</span></span>  
  
     [<span data-ttu-id="5eeb0-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5eeb0-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5eeb0-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5eeb0-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5eeb0-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5eeb0-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5eeb0-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="5eeb0-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5eeb0-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="5eeb0-114">Permissions</span></span>  
 <span data-ttu-id="5eeb0-115">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="5eeb0-115">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="5eeb0-116">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-116">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5eeb0-117">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-117">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="5eeb0-118">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-118">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="5eeb0-119">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-119">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5eeb0-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5eeb0-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="5eeb0-121">Указание в качестве назначения резервного копирования диска или ленты.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-121">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="5eeb0-122">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-122">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5eeb0-123">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-123">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="5eeb0-124">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-124">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="5eeb0-125">Откроется диалоговое окно **Резервное копирование базы данных** .</span><span class="sxs-lookup"><span data-stu-id="5eeb0-125">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="5eeb0-126">В разделе **Назначение** страницы **Общее** выберите **Диск** или **Лента**.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-126">In the **Destination** section of the **General** page, click **Disk** or **Tape**.</span></span> <span data-ttu-id="5eeb0-127">Чтобы выбрать пути к 64 (или менее) дискам или накопителям на магнитной ленте, содержащим один набор носителей, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-127">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span>  
  
     <span data-ttu-id="5eeb0-128">Чтобы удалить носитель резервной копии, выберите его и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-128">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="5eeb0-129">Чтобы просмотреть содержимое носителя резервной копии, выберите его и щелкните **Содержимое**.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-129">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5eeb0-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5eeb0-130">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="5eeb0-131">Указание в качестве назначения резервного копирования диска или ленты.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-131">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="5eeb0-132">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eeb0-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5eeb0-133">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5eeb0-134">В инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) укажите этот файл или устройство и его физическое имя.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the file or device and its physical name.</span></span> <span data-ttu-id="5eeb0-135">В этом примере выполняется резервное копирование базы данных `AdventureWorks2012` в файл на диске `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span><span class="sxs-lookup"><span data-stu-id="5eeb0-135">This example backs up the `AdventureWorks2012` database to the disk file `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eeb0-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="5eeb0-136">See Also</span></span>  
 <span data-ttu-id="5eeb0-137">[Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5eeb0-137">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="5eeb0-138">[Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5eeb0-138">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="5eeb0-139">[Определение логического устройства резервного копирования для дискового файла (SQL Server)](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5eeb0-139">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 <span data-ttu-id="5eeb0-140">[Создание разностной резервной копии базы данных (SQL Server)](create-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5eeb0-140">[Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="5eeb0-141">Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5eeb0-141">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
