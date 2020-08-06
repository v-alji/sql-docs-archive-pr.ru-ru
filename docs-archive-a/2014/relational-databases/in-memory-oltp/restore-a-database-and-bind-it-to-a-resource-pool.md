---
title: Восстановление базы данных и ее привязка к пулу ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0d20a569-8a27-409c-bcab-0effefb48013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0b518c93ca9d5e7157ceaa20d9548d7b6061017d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654277"
---
# <a name="restore-a-database-and-bind-it-to-a-resource-pool"></a><span data-ttu-id="20db5-102">восстановить базу данных и привязать ее к пулу ресурсов</span><span class="sxs-lookup"><span data-stu-id="20db5-102">Restore a Database and Bind it to a Resource Pool</span></span>
  <span data-ttu-id="20db5-103">Даже если у вас имеется достаточно памяти для восстановления базы данных оптимизированными для памяти таблицами, вы хотите следовать рекомендациям и привязать базу данных к именованному пулу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20db5-103">Even though you have enough memory to restore a database with memory-optimized tables, you want to follow best practices and bind the database to a named resource pool.</span></span> <span data-ttu-id="20db5-104">Хотя база данных должна существовать до того, как вы сможете ее привязать к пулу, восстановление вашей базы данных является многоступенчатым процессом.</span><span class="sxs-lookup"><span data-stu-id="20db5-104">Since the database must exist before you can bind it to the pool restoring your database is a multi-step process.</span></span> <span data-ttu-id="20db5-105">Этот раздел поможет выполнить данный процесс.</span><span class="sxs-lookup"><span data-stu-id="20db5-105">This topic walks you through that process.</span></span>  
  
##  <a name="restore-with-norecovery"></a><span data-ttu-id="20db5-106">Восстановление с NORECOVERY</span><span class="sxs-lookup"><span data-stu-id="20db5-106">Restore with NORECOVERY</span></span>  
 <span data-ttu-id="20db5-107">Когда вы восстанавливаете базу данных, NORECOVERY осуществляет создание базы данных и восстановление образа диска без потребления памяти.</span><span class="sxs-lookup"><span data-stu-id="20db5-107">When you restore a database, NORECOVERY causes the database to be created and the disk image restored without consuming memory.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   FROM DISK = 'C:\IMOLTP_test\IMOLTP_DB.bak'  
   WITH NORECOVERY  
```  
  
##  <a name="create-the-resource-pool"></a><span data-ttu-id="20db5-108">Создание пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="20db5-108">Create the resource pool</span></span>  
 <span data-ttu-id="20db5-109">Следующий код [!INCLUDE[tsql](../../includes/tsql-md.md)] создает пул ресурсов с именем Pool_IMOLTP с 50% памяти, доступной для его использования.</span><span class="sxs-lookup"><span data-stu-id="20db5-109">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a resource pool named Pool_IMOLTP with 50% of memory available for its use.</span></span>  <span data-ttu-id="20db5-110">После создания пула Регулятор Ресурсов перенастраивается для включения Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="20db5-110">After the pool is created, the Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
CREATE RESOURCE POOL Pool_IMOLTP WITH (MAX_MEMORY_PERCENT = 50);  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
##  <a name="bind-the-database-and-resource-pool"></a><span data-ttu-id="20db5-111">Привязка базы данных к пулу ресурсов</span><span class="sxs-lookup"><span data-stu-id="20db5-111">Bind the database and resource pool</span></span>  
 <span data-ttu-id="20db5-112">Используйте системную функцию `sp_xtp_bind_db_resource_pool` , чтобы привязать базу данных к пулу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20db5-112">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="20db5-113">Эта функция принимает два параметра: имя базы данных, за которым следует имя пула ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20db5-113">The function takes two parameters: the database name followed by the resource pool name.</span></span>  
  
 <span data-ttu-id="20db5-114">Следующий код [!INCLUDE[tsql](../../includes/tsql-md.md)] определяет привязку базы данных IMOLTP_DB к пулу ресурсов Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="20db5-114">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="20db5-115">Привязка не начнет функционировать до тех пор, пока не будет выполнен следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="20db5-115">The binding does not become effective until you complete the next step.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
##  <a name="restore-with-recovery"></a><span data-ttu-id="20db5-116">Восстановление с RECOVERY</span><span class="sxs-lookup"><span data-stu-id="20db5-116">Restore with RECOVERY</span></span>  
 <span data-ttu-id="20db5-117">При восстановлении базы данных с параметром WITH RECOVERY база данных переводится в режим «в сети» и выполняется восстановление всех данных.</span><span class="sxs-lookup"><span data-stu-id="20db5-117">When you restore the database with recovery the database is brought online and all the data restored.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   WITH RECOVERY  
```  
  
##  <a name="monitor-the-resource-pool-performance"></a><span data-ttu-id="20db5-118">Наблюдение за производительностью пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="20db5-118">Monitor the resource pool performance</span></span>  
 <span data-ttu-id="20db5-119">После того, как база данных привязана к именованному пулу ресурсов и восстановлена параметром recovery, отследите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Объект Статистики Пула Ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20db5-119">Once the database is bound to the named resource pool and restored with recovery, monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Resource Pool Stats Object.</span></span> <span data-ttu-id="20db5-120">Дополнительные сведения см. в разделе [SQL Server, объект Resource Pool Stats](../performance-monitor/sql-server-resource-pool-stats-object.md).</span><span class="sxs-lookup"><span data-stu-id="20db5-120">For more information see [SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20db5-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="20db5-121">See Also</span></span>  
 <span data-ttu-id="20db5-122">[Привязка базы данных с таблицами, оптимизированными для памяти, к пулу ресурсов](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="20db5-122">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span></span>  
 <span data-ttu-id="20db5-123">[sys.sp_xtp_bind_db_resource_pool (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="20db5-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="20db5-124">[SQL Server, объект Resource Pool Stats](../performance-monitor/sql-server-resource-pool-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="20db5-124">[SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md) </span></span>  
 [<span data-ttu-id="20db5-125">sys.dm_resource_governor_resource_pools</span><span class="sxs-lookup"><span data-stu-id="20db5-125">sys.dm_resource_governor_resource_pools</span></span>](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql)  
  
  
