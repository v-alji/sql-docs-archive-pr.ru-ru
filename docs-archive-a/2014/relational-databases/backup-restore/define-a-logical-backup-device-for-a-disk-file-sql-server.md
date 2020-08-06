---
title: Определение логического устройства резервного копирования для дискового файла (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
ms.assetid: 86331d43-c738-4523-ae3d-7d6700348ed1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8aa92296da81f984f260deace887c15f13443b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751239"
---
# <a name="define-a-logical-backup-device-for-a-disk-file-sql-server"></a><span data-ttu-id="baa49-102">Определение логического устройства резервного копирования для дискового файла (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="baa49-102">Define a Logical Backup Device for a Disk File (SQL Server)</span></span>
  <span data-ttu-id="baa49-103">В данном разделе описывается процесс определения логического устройства резервного копирования для дискового файла в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa49-103">This topic describes how to define a logical backup device for a disk file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="baa49-104">Логическое устройство представляет собой определяемое пользователем имя, которое указывает на конкретное физическое устройство резервного копирования (дисковый файл или ленточный накопитель).</span><span class="sxs-lookup"><span data-stu-id="baa49-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="baa49-105">Инициализация физического устройства происходит позже, при записи на него резервной копии.</span><span class="sxs-lookup"><span data-stu-id="baa49-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
 <span data-ttu-id="baa49-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="baa49-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="baa49-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="baa49-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="baa49-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="baa49-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="baa49-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="baa49-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="baa49-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="baa49-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="baa49-111">**Определение логического устройства резервного копирования для дискового файла с помощью:**</span><span class="sxs-lookup"><span data-stu-id="baa49-111">**To define a logical backup device for a disk file, using:**</span></span>  
  
     [<span data-ttu-id="baa49-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="baa49-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="baa49-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="baa49-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="baa49-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="baa49-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="baa49-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="baa49-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="baa49-116">Каждое имя логического устройства должно быть уникальным в пространстве имен всех логических устройств резервного копирования на экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="baa49-116">The logical device name must be unique among all the logical backup devices on the server instance.</span></span> <span data-ttu-id="baa49-117">Чтобы просмотреть имена существующих логических устройств, запросите представление каталога [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="baa49-117">To view the existing logical device names, query the [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) catalog view.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="baa49-118">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="baa49-118">Recommendations</span></span>  
  
-   <span data-ttu-id="baa49-119">Резервные копии, базы данных и журналы рекомендуется хранить на разных дисках.</span><span class="sxs-lookup"><span data-stu-id="baa49-119">We recommend that a backup disk be a different disk than the database data and log disks.</span></span> <span data-ttu-id="baa49-120">Это является необходимым, чтобы можно было гарантировать возможность доступа к резервным копиям при сбое диска с базой данных или журналами.</span><span class="sxs-lookup"><span data-stu-id="baa49-120">This is necessary to make sure that you can access the backups if the data or log disk fails.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="baa49-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="baa49-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="baa49-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="baa49-122">Permissions</span></span>  
 <span data-ttu-id="baa49-123">Требует членства в предопределенной роли сервера **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="baa49-123">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="baa49-124">Необходимо разрешение на запись на жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="baa49-124">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="baa49-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="baa49-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-disk-file"></a><span data-ttu-id="baa49-126">Определение логического устройства резервного копирования для дискового файла</span><span class="sxs-lookup"><span data-stu-id="baa49-126">To define a logical backup device for a disk file</span></span>  
  
1.  <span data-ttu-id="baa49-127">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="baa49-127">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="baa49-128">Разверните **Объекты сервера**и щелкните правой кнопкой мыши **Устройства резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="baa49-128">Expand **Server Objects**, and right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="baa49-129">Выберите команду **Создать устройство резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="baa49-129">Click **New Backup Device**.</span></span> <span data-ttu-id="baa49-130">Откроется диалоговое окно **Устройство резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="baa49-130">The **Backup Device** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="baa49-131">Введите имя устройства.</span><span class="sxs-lookup"><span data-stu-id="baa49-131">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="baa49-132">В качестве места назначения выберите **Файл** и укажите полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="baa49-132">For the destination, click **File** and specify the full path of the file.</span></span>  
  
6.  <span data-ttu-id="baa49-133">Чтобы определить новое устройство, нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="baa49-133">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="baa49-134">Чтобы выполнить резервное копирование на новое устройство, добавьте его в поле **Создать резервную копию на** в диалоговом окне **Резервное копирование базы данных** (**Общие**).</span><span class="sxs-lookup"><span data-stu-id="baa49-134">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="baa49-135">Дополнительные сведения см. в разделе [Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="baa49-135">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="baa49-136">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="baa49-136">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-for-a-disk-file"></a><span data-ttu-id="baa49-137">Определение логического устройства резервного копирования для дискового файла</span><span class="sxs-lookup"><span data-stu-id="baa49-137">To define a logical backup for a disk file</span></span>  
  
1.  <span data-ttu-id="baa49-138">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa49-138">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa49-139">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="baa49-139">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa49-140">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="baa49-140">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="baa49-141">Этот пример иллюстрирует использование процедуры [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) в целях определения логического устройства резервного копирования для дискового файла.</span><span class="sxs-lookup"><span data-stu-id="baa49-141">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a disk file.</span></span> <span data-ttu-id="baa49-142">В этом примере добавляется дисковое устройство резервного копирования с именем `mydiskdump`, которое имеет физическое имя `c:\dump\dump1.bak`.</span><span class="sxs-lookup"><span data-stu-id="baa49-142">The example adds the disk backup device named `mydiskdump`, with the physical name `c:\dump\dump1.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mydiskdump', 'c:\dump\dump1.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="baa49-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="baa49-143">See Also</span></span>  
 <span data-ttu-id="baa49-144">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa49-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="baa49-145">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="baa49-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="baa49-146">[sys.backup_devices (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa49-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="baa49-147">[sp_addumpdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa49-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="baa49-148">[sp_dropdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="baa49-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="baa49-149">[Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="baa49-149">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="baa49-150">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="baa49-150">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
