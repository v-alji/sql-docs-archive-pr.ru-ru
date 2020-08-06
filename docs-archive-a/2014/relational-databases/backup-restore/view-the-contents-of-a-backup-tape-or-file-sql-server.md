---
title: Просмотр содержимого ленты или файла резервной копии (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- displaying backup content
- viewing backup content
- tape backup devices, viewing contents
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
ms.assetid: cd6674a2-ca55-4b5a-a971-878ba001821e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 044519b64d41fbbdfc9302ce24369ab282727f67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734178"
---
# <a name="view-the-contents-of-a-backup-tape-or-file-sql-server"></a><span data-ttu-id="35f95-102">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="35f95-102">View the Contents of a Backup Tape or File (SQL Server)</span></span>
  <span data-ttu-id="35f95-103">В этом разделе описывается просмотр содержимого ленты или файла резервной копии в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35f95-103">This topic describes how to view the content of a backup tape or file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35f95-104">Поддержка резервного копирования на ленточные устройства будет исключена в будущей версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35f95-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="35f95-105">Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется.</span><span class="sxs-lookup"><span data-stu-id="35f95-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="35f95-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="35f95-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="35f95-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="35f95-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="35f95-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="35f95-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="35f95-109">**Просмотр содержимого ленты или файла резервной копии с помощью следующих средств**</span><span class="sxs-lookup"><span data-stu-id="35f95-109">**To view the content of a backup tape or file, using:**</span></span>  
  
     [<span data-ttu-id="35f95-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35f95-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="35f95-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35f95-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="35f95-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="35f95-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="35f95-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="35f95-113">Security</span></span>  
 <span data-ttu-id="35f95-114">Сведения о безопасности см. в статье [RESTORE HEADERONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="35f95-114">For information about security, see [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="35f95-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="35f95-115">Permissions</span></span>  
 <span data-ttu-id="35f95-116">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздних версиях для получения сведений о резервном наборе данных или устройстве резервного копирования необходимо разрешение CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="35f95-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="35f95-117">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений для базы данных (Transact-SQL)](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="35f95-117">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="35f95-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35f95-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="35f95-119">Просмотр содержимого ленты или файла резервной копии</span><span class="sxs-lookup"><span data-stu-id="35f95-119">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="35f95-120">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="35f95-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="35f95-121">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="35f95-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="35f95-122">Щелкните правой кнопкой мыши базу данных, резервную копию которой хотите создать, укажите пункт **Задачи**и выберите команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="35f95-122">Right-click the database you want to backup, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="35f95-123">Откроется диалоговое окно **Резервное копирование базы данных** .</span><span class="sxs-lookup"><span data-stu-id="35f95-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="35f95-124">В области **Назначение** страницы **Общие** выберите **Диск** или **Лента**.</span><span class="sxs-lookup"><span data-stu-id="35f95-124">In the **Destination** section of the **General** page, click either **Disk** or **Tape**.</span></span> <span data-ttu-id="35f95-125">В списке **Создать резервную копию на** выберите нужный файл на диске или ленту.</span><span class="sxs-lookup"><span data-stu-id="35f95-125">In the **Back up to** list box, look for the disk file or tape you want.</span></span>  
  
     <span data-ttu-id="35f95-126">Если дисковый файл или лента отсутствуют в списке, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="35f95-126">If the disk file or tape is not displayed in the list-box, click **Add**.</span></span> <span data-ttu-id="35f95-127">Выберите имя файла или ленточный накопитель.</span><span class="sxs-lookup"><span data-stu-id="35f95-127">Select a file name or tape drive.</span></span> <span data-ttu-id="35f95-128">Чтобы добавить его в список **Создать резервную копию на** , нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="35f95-128">To add it to the **Back up to** list-box, click **OK**.</span></span>  
  
5.  <span data-ttu-id="35f95-129">В списке **Создать резервную копию на** выберите путь к диску или ленточному накопителю, который необходимо просмотреть, и нажмите кнопку **Содержимое**.</span><span class="sxs-lookup"><span data-stu-id="35f95-129">In the **Back up to** list-box, select the path of the disk or tape drive you want to view, and click **Contents**.</span></span> <span data-ttu-id="35f95-130">Откроется диалоговое окно **Содержимое устройства** .</span><span class="sxs-lookup"><span data-stu-id="35f95-130">This opens the **Device Contents** dialog box.</span></span>  
  
6.  <span data-ttu-id="35f95-131">На правой панели выводятся сведения о наборе носителей и резервных наборах данных на выбранной ленте или в файле.</span><span class="sxs-lookup"><span data-stu-id="35f95-131">The right-hand pane displays information about the media set and backup sets on the selected tape or file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="35f95-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35f95-132">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="35f95-133">Просмотр содержимого ленты или файла резервной копии</span><span class="sxs-lookup"><span data-stu-id="35f95-133">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="35f95-134">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35f95-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="35f95-135">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="35f95-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="35f95-136">Используйте инструкцию [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="35f95-136">Use the [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) statement.</span></span> <span data-ttu-id="35f95-137">Этот пример возвращает сведения о файле `AdventureWorks2012-FullBackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="35f95-137">This example returns information about the file named `AdventureWorks2012-FullBackup.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
RESTORE HEADERONLY   
FROM DISK = N'C:\AdventureWorks2012-FullBackup.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="35f95-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="35f95-138">See Also</span></span>  
 <span data-ttu-id="35f95-139">[backupfilegroup (Transact-SQL)](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="35f95-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="35f95-140">[backupfile (Transact-SQL)](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="35f95-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="35f95-141">[backupset (Transact-SQL)](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="35f95-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="35f95-142">[backupmediaset (Transact-SQL)](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="35f95-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="35f95-143">[backupmediafamily (Transact-SQL)](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="35f95-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="35f95-144">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35f95-144">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="35f95-145">[Определение логического устройства резервного копирования для дискового файла (SQL Server)](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35f95-145">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="35f95-146">Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="35f95-146">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
