---
title: Определение логического устройства резервного копирования для ленточного накопителя (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- tape backup devices, creating
ms.assetid: 66f36e1d-0287-4fac-8a51-71f9f0d7ad5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8728df2cc0b5907e51da84ed9e77d897a1718d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751232"
---
# <a name="define-a-logical-backup-device-for-a-tape-drive-sql-server"></a><span data-ttu-id="f3805-102">Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f3805-102">Define a Logical Backup Device for a Tape Drive (SQL Server)</span></span>
  <span data-ttu-id="f3805-103">В данном разделе описывается процесс определения логического устройства резервного копирования для ленточного накопителя в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3805-103">This topic describes how to define a logical backup device for a tape drive in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f3805-104">Логическое устройство представляет собой определяемое пользователем имя, которое указывает на конкретное физическое устройство резервного копирования (дисковый файл или ленточный накопитель).</span><span class="sxs-lookup"><span data-stu-id="f3805-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="f3805-105">Инициализация физического устройства происходит позже, при записи на него резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f3805-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3805-106">Поддержка ленточных устройств резервного копирования будет удалена в одной из будущих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3805-106">Support for tape backup devices will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3805-107">Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется.</span><span class="sxs-lookup"><span data-stu-id="f3805-107">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="f3805-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f3805-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f3805-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f3805-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f3805-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f3805-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f3805-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f3805-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f3805-112">**Определение логического устройства резервного копирования для ленточного накопителя с помощью:**</span><span class="sxs-lookup"><span data-stu-id="f3805-112">**To define a logical backup device for a tape drive, using:**</span></span>  
  
     [<span data-ttu-id="f3805-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3805-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f3805-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3805-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f3805-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f3805-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f3805-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f3805-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f3805-117">Ленточный накопитель или диски должны поддерживаться операционной системой Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f3805-117">The tape drive or drives must be supported by the Microsoft Windows operating system.</span></span>  
  
-   <span data-ttu-id="f3805-118">Ленточное устройство должно быть физически подключено к компьютеру, на котором запущен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3805-118">The tape device must be connected physically to the computer that is running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f3805-119">Резервное копирование на удаленный ленточный накопитель не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3805-119">Backing up to remote tape devices is not supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f3805-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="f3805-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f3805-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="f3805-121">Permissions</span></span>  
 <span data-ttu-id="f3805-122">Требует членства в предопределенной роли сервера **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="f3805-122">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="f3805-123">Необходимо разрешение на запись на жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="f3805-123">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f3805-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f3805-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="f3805-125">Определение логического устройства резервного копирования для ленточного накопителя</span><span class="sxs-lookup"><span data-stu-id="f3805-125">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="f3805-126">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="f3805-126">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f3805-127">Разверните узел **Объекты сервера**и щелкните правой кнопкой мыши пункт **Устройства резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="f3805-127">Expand **Server Objects**, and then right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="f3805-128">Выберите пункт **Новое устройство резервного копирования**, в результате чего появится диалоговое окно **Устройство резервного копирования** .</span><span class="sxs-lookup"><span data-stu-id="f3805-128">Click **New Backup Device**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="f3805-129">Введите имя устройства.</span><span class="sxs-lookup"><span data-stu-id="f3805-129">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="f3805-130">В разделе «Расположение» установите переключатель **Лента** и выберите ленточный накопитель, который еще не связан с другим устройством резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="f3805-130">For the destination, click **Tape** and select a tape drive that is not already associated with another backup device.</span></span> <span data-ttu-id="f3805-131">Если таких накопителей нет, не устанавливайте переключатель **Лента** .</span><span class="sxs-lookup"><span data-stu-id="f3805-131">If no such tape drives are available, the **Tape** option is inactive.</span></span>  
  
6.  <span data-ttu-id="f3805-132">Чтобы определить новое устройство, нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3805-132">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="f3805-133">Чтобы выполнить резервное копирование на новое устройство, добавьте его в поле **Создать резервную копию на** в диалоговом окне **Резервное копирование базы данных** (**Общие**).</span><span class="sxs-lookup"><span data-stu-id="f3805-133">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="f3805-134">Дополнительные сведения см. в разделе [Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f3805-134">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f3805-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f3805-135">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="f3805-136">Определение логического устройства резервного копирования для ленточного накопителя</span><span class="sxs-lookup"><span data-stu-id="f3805-136">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="f3805-137">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3805-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f3805-138">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f3805-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f3805-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f3805-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f3805-140">Этот пример иллюстрирует использование процедуры [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) в целях определения логического устройства резервного копирования для ленточного накопителя.</span><span class="sxs-lookup"><span data-stu-id="f3805-140">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a tape.</span></span> <span data-ttu-id="f3805-141">В этом примере добавляется ленточное устройство резервного копирования с именем `tapedump1`, которое имеет физическое имя `\\.\tape0`.</span><span class="sxs-lookup"><span data-stu-id="f3805-141">The example adds the tape backup device named `tapedump1`, with the physical name `\\.\tape0`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'tape', 'tapedump1', '\\.\tape0' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3805-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3805-142">See Also</span></span>  
 <span data-ttu-id="f3805-143">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f3805-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="f3805-144">[sys.backup_devices (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f3805-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="f3805-145">[sp_addumpdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f3805-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="f3805-146">[sp_dropdevice (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f3805-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="f3805-147">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3805-147">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="f3805-148">[Определение логического устройства резервного копирования для дискового файла (SQL Server)](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f3805-148">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="f3805-149">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f3805-149">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
