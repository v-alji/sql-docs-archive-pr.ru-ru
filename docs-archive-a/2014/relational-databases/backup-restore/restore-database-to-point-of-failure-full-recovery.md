---
title: Восстановление базы данных до точки сбоя в модели полного восстановления (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- point of failure [SQL Server]
- restoring databases [SQL Server], point of failure
- database restores [SQL Server], point of failure
ms.assetid: 04106e18-bbf7-4a5e-a2e1-3d65319814d5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95b73660ebb44f4daffe6eaefd873699cfbbd8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658838"
---
# <a name="restore-a-database-to-the-point-of-failure-under-the-full-recovery-model-transact-sql"></a><span data-ttu-id="2f266-102">Восстановление базы данных до точки сбоя в модели полного восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2f266-102">Restore a Database to the Point of Failure Under the Full Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="2f266-103">В этом подразделе описывается восстановление до точки сбоя.</span><span class="sxs-lookup"><span data-stu-id="2f266-103">This topic explains how to restore to the point of failure.</span></span> <span data-ttu-id="2f266-104">Сведения в этом разделе относятся только к тем базам данных, которые используют модель полного восстановления или модель восстановления с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="2f266-104">The topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
### <a name="to-restore-to-the-point-of-failure"></a><span data-ttu-id="2f266-105">Восстановление до точки сбоя</span><span class="sxs-lookup"><span data-stu-id="2f266-105">To restore to the point of failure</span></span>  
  
1.  <span data-ttu-id="2f266-106">Создайте резервную копию заключительного фрагмента журнала базы данных, взяв за основу следующую инструкцию [BACKUP](/sql/t-sql/statements/backup-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="2f266-106">Back up the tail of the log by running the following basic [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
    ```  
    BACKUP LOG <database_name> TO <backup_device>   
       WITH NORECOVERY, NO_TRUNCATE;  
    ```  
  
2.  <span data-ttu-id="2f266-107">Восстановите базу данных из ее полной резервной копии, взяв за основу следующую инструкцию [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="2f266-107">Restore a full database backup by running the following basic [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
3.  <span data-ttu-id="2f266-108">Можно также восстановить базу данных из ее разностной резервной копии, взяв за основу следующую инструкцию RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="2f266-108">Optionally, restore a differential database backup by running the following basic RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
4.  <span data-ttu-id="2f266-109">Примените все журналы транзакций, включая резервную копию заключительного фрагмента журнала (созданную на первом шаге), указав предложение WITH NORECOVERY в инструкции RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="2f266-109">Apply each transaction log, including the tail-log backup you created in step 1, by specifying WITH NORECOVERY in the RESTORE LOG statement:</span></span>  
  
    ```  
    RESTORE LOG <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
5.  <span data-ttu-id="2f266-110">Восстановите базу данных, выполнив следующую инструкцию RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="2f266-110">Recover the database by running the following RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name>   
       WITH RECOVERY;  
    ```  
  
## <a name="example"></a><span data-ttu-id="2f266-111">Пример</span><span class="sxs-lookup"><span data-stu-id="2f266-111">Example</span></span>  
 <span data-ttu-id="2f266-112">Перед запуском этого примера необходимо завершить следующие подготовительные действия.</span><span class="sxs-lookup"><span data-stu-id="2f266-112">Before you can run the example, you must complete the following preparations:</span></span>  
  
1.  <span data-ttu-id="2f266-113">По умолчанию, база данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] имеет простую модель восстановления.</span><span class="sxs-lookup"><span data-stu-id="2f266-113">The default recovery model of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is the simple recovery model.</span></span> <span data-ttu-id="2f266-114">Поскольку в этой модели не поддерживается восстановление до момента сбоя, настройте [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] на использование модели полного восстановления, выполнив следующую инструкцию [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="2f266-114">Because this recovery model does not support restoring to the point of a failure, set [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] to use the full recovery model by running the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
    ```  
  
2.  <span data-ttu-id="2f266-115">Создайте полную резервную копию базы данных при помощи следующей инструкции BACKUP:</span><span class="sxs-lookup"><span data-stu-id="2f266-115">Create a full database back of the database by using the following BACKUP statement:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Data.bck';  
    ```  
  
3.  <span data-ttu-id="2f266-116">Создайте резервную копию журналов:</span><span class="sxs-lookup"><span data-stu-id="2f266-116">Create a routine log backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Log.bck';  
    ```  
  
 <span data-ttu-id="2f266-117">В следующем примере после создания резервной копии заключительного фрагмента журнала базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] производится восстановление ранее созданной резервной копии</span><span class="sxs-lookup"><span data-stu-id="2f266-117">The following example restores the backups that are created previously, after creating a tail-log backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="2f266-118">(на этом шаге предполагается, что имеется доступ к диску, на котором хранятся журналы).</span><span class="sxs-lookup"><span data-stu-id="2f266-118">(This step assumes that the log disk can be accessed.)</span></span>  
  
 <span data-ttu-id="2f266-119">Вначале создается резервная копия заключительного фрагмента журнала базы данных, которая захватывает активный журнал и оставляет базу данных в состоянии восстановления.</span><span class="sxs-lookup"><span data-stu-id="2f266-119">First, the example creates a tail-log backup of the database that captures the active log and leaves the database in the Restoring state.</span></span> <span data-ttu-id="2f266-120">После этого в данном примере производится восстановление резервной копии базы данных, применяется раннее созданная процедура резервного копирования журналов и создается резервная копия заключительного фрагмента журнала.</span><span class="sxs-lookup"><span data-stu-id="2f266-120">Then, the example restores the database backup, applies the routine log backup created previously, and applies the tail-log backup.</span></span> <span data-ttu-id="2f266-121">Наконец, отдельным шагом производится восстановление базы данных.</span><span class="sxs-lookup"><span data-stu-id="2f266-121">Finally, the example recovers the database in a separate step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f266-122">По умолчанию, при обработке инструкции, выполняющей окончательное восстановление резервной копии, производится восстановление базы данных.</span><span class="sxs-lookup"><span data-stu-id="2f266-122">The default behavior is to recover a database as part of the statement that restores the final backup.</span></span>  
  
```  
/* Example of restoring a to the point of failure */  
-- Step 1: Create a tail-log backup by using WITH NORECOVERY.  
BACKUP LOG AdventureWorks2012  
   TO DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 2: Restore the full database backup.  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Data.bck'  
   WITH NORECOVERY;  
GO  
-- Step 3: Restore the first transaction log backup.  
RESTORE LOG AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 4: Restore the tail-log backup.  
RESTORE LOG AdventureWorks2012  
   FROM  DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 5: Recover the database.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f266-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f266-123">See Also</span></span>  
 <span data-ttu-id="2f266-124">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f266-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="2f266-125">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2f266-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
