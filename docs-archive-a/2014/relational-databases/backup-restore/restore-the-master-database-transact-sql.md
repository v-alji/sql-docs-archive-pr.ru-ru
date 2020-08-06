---
title: Восстановление базы данных master (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- master database [SQL Server], restoring
ms.assetid: c83d802c-e84e-4458-b3ca-173d9ba32f73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c9cb078b7af60fc5e060bcb144fc9cbaee8ecf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666675"
---
# <a name="restore-the-master-database-transact-sql"></a><span data-ttu-id="04ffe-102">восстановить базу данных master (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="04ffe-102">Restore the master Database (Transact-SQL)</span></span>
  <span data-ttu-id="04ffe-103">Этот раздел посвящен восстановлению базы данных **master** из полной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="04ffe-103">This topic explains how to restore the **master** database from a full database backup.</span></span>  
  
### <a name="to-restore-the-master-database"></a><span data-ttu-id="04ffe-104">Восстановление базы данных master</span><span class="sxs-lookup"><span data-stu-id="04ffe-104">To restore the master database</span></span>  
  
1.  <span data-ttu-id="04ffe-105">Запустите экземпляр сервера в однопользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="04ffe-105">Start the server instance in single-user mode.</span></span>  
  
     <span data-ttu-id="04ffe-106">Дополнительные сведения об указании параметра запуска в однопользовательском режиме ( **-m**) см. в разделе [Настройка параметров запуска сервера (диспетчер конфигурации SQL Server)](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="04ffe-106">For information about how to specify the single-user startup parameter (**-m**), see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
2.  <span data-ttu-id="04ffe-107">Чтобы восстановить полную резервную копию базы данных **master**, используйте следующую инструкцию [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="04ffe-107">To restore a full database backup of **master**, use the following [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="04ffe-108">`RESTORE DATABASE master FROM`  *<резервное устройство>*  `WITH REPLACE`</span><span class="sxs-lookup"><span data-stu-id="04ffe-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span></span>  
  
     <span data-ttu-id="04ffe-109">Если задан параметр REPLACE, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] восстанавливает указанную базу данных, даже если база данных с таким же именем уже существует.</span><span class="sxs-lookup"><span data-stu-id="04ffe-109">The REPLACE option instructs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to restore the specified database even when a database of the same name already exists.</span></span> <span data-ttu-id="04ffe-110">Существующая база данных в таком случае будет удалена.</span><span class="sxs-lookup"><span data-stu-id="04ffe-110">The existing database, if any, is deleted.</span></span> <span data-ttu-id="04ffe-111">В однопользовательском режиме рекомендуется вводить инструкцию RESTORE DATABASE в [программе sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="04ffe-111">In single-user mode, we recommend that you enter the RESTORE DATABASE statement in the [sqlcmd utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="04ffe-112">Дополнительные сведения см. в статье [Программа sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="04ffe-112">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="04ffe-113">После восстановления базы данных **master** экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] завершает работу и останавливает процесс **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="04ffe-113">After **master** is restored, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] shuts down and terminates the **sqlcmd** process.</span></span> <span data-ttu-id="04ffe-114">Перед перезапуском экземпляра сервера удалите параметр запуска однопользовательского режима.</span><span class="sxs-lookup"><span data-stu-id="04ffe-114">Before you restart the server instance, remove the single-user startup parameter.</span></span> <span data-ttu-id="04ffe-115">Дополнительные сведения см. в разделе [Настройка параметров запуска сервера (диспетчер конфигурации SQL Server)](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="04ffe-115">For more information, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
3.  <span data-ttu-id="04ffe-116">Перезапустите экземпляр сервера и выполните остальные шаги восстановления из копии, такие как восстановление других баз данных, присоединение баз данных и исправление несовпадающих данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="04ffe-116">Restart the server instance and continue other recovery steps such as restoring other databases, attaching databases, and correcting user mismatches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04ffe-117">Пример</span><span class="sxs-lookup"><span data-stu-id="04ffe-117">Example</span></span>  
 <span data-ttu-id="04ffe-118">Следующий пример восстанавливает базу данных `master` в определенном по умолчанию экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="04ffe-118">The following example restores the `master` database on the default server instance.</span></span> <span data-ttu-id="04ffe-119">В этом примере предполагается, что экземпляр сервера уже работает в однопользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="04ffe-119">The example assumes that the server instance is already running in single-user mode.</span></span> <span data-ttu-id="04ffe-120">В примере запускается `sqlcmd` и выполняется инструкция `RESTORE DATABASE` , которая восстанавливает полную резервную копию базы данных `master` с дискового устройства: `Z:\SQLServerBackups\master.bak`.</span><span class="sxs-lookup"><span data-stu-id="04ffe-120">The example starts `sqlcmd` and executes a `RESTORE DATABASE` statement that restores a full database backup of `master` from a disk device: `Z:\SQLServerBackups\master.bak`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04ffe-121">Для именованного экземпляра команда **sqlcmd** должна указывать параметр **-S** _\<ComputerName>_ \\ *\<InstanceName>* .</span><span class="sxs-lookup"><span data-stu-id="04ffe-121">For a named instance, the **sqlcmd** command must specify the **-S**_\<ComputerName>_\\*\<InstanceName>* option.</span></span>  
  
```  
  
      C:\> sqlcmd  
1> RESTORE DATABASE master FROM DISK = 'Z:\SQLServerBackups\master.bak' WITH REPLACE;  
2> GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="04ffe-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="04ffe-122">See Also</span></span>  
 <span data-ttu-id="04ffe-123">[Выполнение полного восстановления базы данных (простая модель восстановления)](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-123">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="04ffe-124">[Выполнение полного восстановления базы данных (модель полного восстановления)](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-124">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="04ffe-125">[Диагностика пользователей, утративших связь с учетной записью (SQL Server)](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-125">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 <span data-ttu-id="04ffe-126">[Присоединение и отсоединение базы данных (SQL Server)](../databases/database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-126">[Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="04ffe-127">[Перестроение системных баз данных](../databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-127">[Rebuild System Databases](../databases/system-databases.md) </span></span>  
 <span data-ttu-id="04ffe-128">[Параметры запуска службы Database Engine](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-128">[Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span></span>  
 <span data-ttu-id="04ffe-129">[Диспетчер конфигурации SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-129">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="04ffe-130">[Резервное копирование и восстановление системных баз данных (SQL Server)](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="04ffe-130">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="04ffe-131">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04ffe-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="04ffe-132">Запуск SQL Server в однопользовательском режиме</span><span class="sxs-lookup"><span data-stu-id="04ffe-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
