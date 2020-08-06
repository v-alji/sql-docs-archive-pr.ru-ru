---
title: Удаление устройства резервного копирования (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], deleting devices
- backup devices [SQL Server], deleting
- deleting backup devices
- removing backup devices
- backing up databases [SQL Server], backup devices
ms.assetid: 7be62480-ed6a-4262-a071-1feba73b1c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8734e587a8ecde315fb17120511455a59e38901
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658851"
---
# <a name="delete-a-backup-device-sql-server"></a><span data-ttu-id="47a07-102">Удаление устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="47a07-102">Delete a Backup Device (SQL Server)</span></span>
  <span data-ttu-id="47a07-103">В этом разделе описывается, как удалить резервное устройство в среде [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47a07-103">This topic describes how to delete a backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="47a07-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="47a07-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="47a07-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="47a07-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="47a07-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="47a07-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="47a07-107">**Удаление устройства резервного копирования с помощью:**</span><span class="sxs-lookup"><span data-stu-id="47a07-107">**To delete a backup device, using:**</span></span>  
  
     [<span data-ttu-id="47a07-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="47a07-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="47a07-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="47a07-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="47a07-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="47a07-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="47a07-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="47a07-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="47a07-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="47a07-112">Permissions</span></span>  
 <span data-ttu-id="47a07-113">Требует членства в предопределенной роли сервера **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="47a07-113">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="47a07-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="47a07-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="47a07-115">Удаление устройства резервного копирования</span><span class="sxs-lookup"><span data-stu-id="47a07-115">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="47a07-116">После подключения к соответствующему экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="47a07-116">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="47a07-117">Разверните узел **Объекты сервера**, затем разверните узел **Устройства резервного копирования**.</span><span class="sxs-lookup"><span data-stu-id="47a07-117">Expand **Server Objects**, and then expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="47a07-118">Щелкните правой кнопкой мыши устройство, которое нужно удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="47a07-118">Right-click the device you want, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="47a07-119">В диалоговом окне **Удаление объекта** убедитесь, что в столбце **Имя объекта** отображается нужное имя.</span><span class="sxs-lookup"><span data-stu-id="47a07-119">In the **Delete Object** dialog box, verify that the correct device name appears in the **Object Name** column.</span></span>  
  
5.  <span data-ttu-id="47a07-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="47a07-120">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="47a07-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="47a07-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="47a07-122">Удаление устройства резервного копирования</span><span class="sxs-lookup"><span data-stu-id="47a07-122">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="47a07-123">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47a07-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="47a07-124">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="47a07-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="47a07-125">Скопируйте следующий пример в запрос.</span><span class="sxs-lookup"><span data-stu-id="47a07-125">Copy and paste the following example into the query.</span></span> <span data-ttu-id="47a07-126">В этом примере показано, как использовать инструкцию [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) для удаления устройства резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="47a07-126">This example shows how to use [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) to delete a backup device.</span></span> <span data-ttu-id="47a07-127">Выполните первый пример для создания устройства резервного копирования `mybackupdisk` и физического имени `c:\backup\backup1.bak`.</span><span class="sxs-lookup"><span data-stu-id="47a07-127">Execute the first example to create the `mybackupdisk` backup device and the physical name `c:\backup\backup1.bak`.</span></span> <span data-ttu-id="47a07-128">Выполните инструкцию `sp_dropdevice` для удаления устройства резервного копирования `mybackupdisk`.</span><span class="sxs-lookup"><span data-stu-id="47a07-128">Execute `sp_dropdevice` to delete the `mybackupdisk` backup device.</span></span> <span data-ttu-id="47a07-129">Параметр `delfile` удаляет физическое имя.</span><span class="sxs-lookup"><span data-stu-id="47a07-129">The `delfile` parameter deletes the physical name.</span></span>  
  
```sql  
--Define a backup device and physical name.   
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mybackupdisk', 'c:\backup\backup1.bak' ;  
GO  
--Delete the backup device and the physical name.  
USE AdventureWorks2012 ;  
GO  
EXEC sp_dropdevice ' mybackupdisk ', 'delfile' ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="47a07-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="47a07-130">See Also</span></span>  
 <span data-ttu-id="47a07-131">[Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="47a07-131">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="47a07-132">[sys.backup_devices (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47a07-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="47a07-133">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47a07-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="47a07-134">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="47a07-134">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="47a07-135">sp_addumpdevice (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="47a07-135">sp_addumpdevice &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)  
  
  
