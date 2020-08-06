---
title: Поэтапное восстановление баз данных с оптимизированными для памяти таблицами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 732c9721-8dd4-481d-8ff9-1feaaa63f84f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed23f08d40e23b1d43c1b642f4089fe77646b675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738375"
---
# <a name="piecemeal-restore-of-databases-with-memory-optimized-tables"></a><span data-ttu-id="790e3-102">Поэтапное восстановление баз данных с таблицами, оптимизированными для памяти</span><span class="sxs-lookup"><span data-stu-id="790e3-102">Piecemeal Restore of Databases With Memory-Optimized Tables</span></span>
  <span data-ttu-id="790e3-103">Поэтапное восстановление поддерживается в базах данных с таблицами, оптимизированными для памяти, за исключением одного случая, описанного ниже.</span><span class="sxs-lookup"><span data-stu-id="790e3-103">Piecemeal restore is supported on databases with memory-optimized tables except for one restriction described below.</span></span> <span data-ttu-id="790e3-104">Дополнительные сведения о поэтапном резервном копировании и восстановлении см. в разделах [RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) и [Поэтапное восстановление (SQL Server)](../backup-restore/piecemeal-restores-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="790e3-104">For more information about piecemeal backup and restore, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [Piecemeal Restores &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span></span>  
  
 <span data-ttu-id="790e3-105">Файловая группа, оптимизированная для памяти, должна подвергаться резервному копированию и восстанавливаться вместе с первичной файловой группой.</span><span class="sxs-lookup"><span data-stu-id="790e3-105">A memory-optimized filegroup must be backed up and restored together with the primary filegroup:</span></span>  
  
-   <span data-ttu-id="790e3-106">При резервном копировании (или восстановлении) первичной файловой группы необходимо указать оптимизированную для памяти файловую группу.</span><span class="sxs-lookup"><span data-stu-id="790e3-106">If you back up (or restore) the primary filegroup you must specify the memory-optimized filegroup.</span></span>  
  
-   <span data-ttu-id="790e3-107">При резервном копировании (или восстановлении) файловой группы, оптимизированной для памяти, необходимо указать первичную файловую группу.</span><span class="sxs-lookup"><span data-stu-id="790e3-107">If you backup (or restore) the memory-optimized filegroup you must specify the primary filegroup.</span></span>  
  
 <span data-ttu-id="790e3-108">Основные сценарии для поэтапного резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="790e3-108">Key scenarios for piecemeal backup and restore are,</span></span>  
  
-   <span data-ttu-id="790e3-109">Поэтапное резервное копирование позволяет уменьшить размер копии.</span><span class="sxs-lookup"><span data-stu-id="790e3-109">Piecemeal backup allows you to reduce the size of backup.</span></span> <span data-ttu-id="790e3-110">Некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="790e3-110">Some examples:</span></span>  
  
    -   <span data-ttu-id="790e3-111">Настройка резервного копирования базы данных на выполнение в разные моменты времени, чтобы свести к минимуму влияние этого процесса на рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="790e3-111">Configure the database backup to occur at different times or days to minimize the impact on the workload.</span></span> <span data-ttu-id="790e3-112">Одним из примеров будет очень крупная база данных (больше 1 ТБ), где полное резервное копирование базы данных не может быть выполнено за время, отведенное для обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="790e3-112">One example is a very large database (greater than 1 TB) where a full database backup cannot complete in the time allocated for database maintenance.</span></span> <span data-ttu-id="790e3-113">В этой ситуации можно использовать поэтапное резервное копирование всей базы за несколько этапов.</span><span class="sxs-lookup"><span data-stu-id="790e3-113">In that situation, you can use piecemeal backup to backup the full database in multiple piecemeal backups.</span></span>  
  
    -   <span data-ttu-id="790e3-114">Если файловая группа помечена как доступная только для чтения, то не требуется резервное копирование журнала транзакций после того, как группа было помечена как только для чтения.</span><span class="sxs-lookup"><span data-stu-id="790e3-114">If a filegroup is marked read-only, it does not require a transaction log backup after it was marked read-only.</span></span> <span data-ttu-id="790e3-115">Можно выбрать вариант разового резервного копирования файловой группы после того, как она будет помечена как группа только для чтения.</span><span class="sxs-lookup"><span data-stu-id="790e3-115">You can choose to back up the filegroup only once after marking it read-only.</span></span>  
  
-   <span data-ttu-id="790e3-116">Поэтапное восстановление.</span><span class="sxs-lookup"><span data-stu-id="790e3-116">Piecemeal restore.</span></span>  
  
    -   <span data-ttu-id="790e3-117">Цель поэтапного восстановления — перевести критические части базы данных в рабочий режим, не ожидая поступления всех данных.</span><span class="sxs-lookup"><span data-stu-id="790e3-117">The goal of a piecemeal restore is to bring the critical parts of database online without waiting for all the data.</span></span> <span data-ttu-id="790e3-118">Одним из примеров будет таков: база данных имеет секционированные данные, причем старые секции используются только изредка.</span><span class="sxs-lookup"><span data-stu-id="790e3-118">One example is if a database has partitioned data, such that older partitions are only used rarely.</span></span> <span data-ttu-id="790e3-119">Их можно восстановить только по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="790e3-119">You can restore them only on an as-needed basis.</span></span> <span data-ttu-id="790e3-120">То же верно и для файловых групп, содержащих, например, исторические данные.</span><span class="sxs-lookup"><span data-stu-id="790e3-120">Similar for filegroups that contain, for example, historical data.</span></span>  
  
    -   <span data-ttu-id="790e3-121">С помощью восстановления страниц можно исправить именно поврежденные страницы.</span><span class="sxs-lookup"><span data-stu-id="790e3-121">Using page repair, you can fix page corruption by specifically restoring the page.</span></span> <span data-ttu-id="790e3-122">Дополнительные сведения см. в разделе [Восстановление страниц (SQL Server)](../backup-restore/restore-pages-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="790e3-122">For more information, see [Restore Pages &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span></span>  
  
## <a name="samples"></a><span data-ttu-id="790e3-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="790e3-123">Samples</span></span>  
 <span data-ttu-id="790e3-124">В примерах используется следующая схема:</span><span class="sxs-lookup"><span data-stu-id="790e3-124">The examples use the following schema:</span></span>  
  
```  
CREATE DATABASE imoltp  
ON PRIMARY (name = imoltp_primary1, filename = 'c:\data\imoltp_data1.mdf')  
LOG ON (name = imoltp_log, filename = 'c:\data\imoltp_log.ldf')  
GO  
  
ALTER DATABASE imoltp ADD FILE (name = imoltp_primary2, filename = 'c:\data\imoltp_data2.ndf')  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_secondary  
ALTER DATABASE imoltp ADD FILE (name = imoltp_secondary, filename = 'c:\data\imoltp_secondary.ndf') TO FILEGROUP imoltp_secondary  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_mod CONTAINS MEMORY_OPTIMIZED_DATA   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod1', filename='c:\data\imoltp_mod1') TO FILEGROUP imoltp_mod   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod2', filename='c:\data\imoltp_mod2') TO FILEGROUP imoltp_mod   
GO  
```  
  
### <a name="backup"></a><span data-ttu-id="790e3-125">Резервное копирование</span><span class="sxs-lookup"><span data-stu-id="790e3-125">Backup</span></span>  
 <span data-ttu-id="790e3-126">Этот пример показывает, как создать резервную копию первичной файловой группы и группы, оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="790e3-126">This sample shows how to backup the primary filegroup and the memory-optimized filegroup.</span></span> <span data-ttu-id="790e3-127">Следует совместно указать и оптимизированную для памяти группу, и первичную файловую группу.</span><span class="sxs-lookup"><span data-stu-id="790e3-127">You must specify both primary and memory-optimized filegroup together.</span></span>  
  
```  
backup database imoltp filegroup='primary', filegroup='imoltp_mod' to disk='c:\data\imoltp.dmp' with init  
```  
  
 <span data-ttu-id="790e3-128">Следующий пример показывает, что резервное копирование файловой группы (или групп), отличной от первичной и оптимизированной для памяти файловой группы, выполняется так же, как и для баз данных без таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="790e3-128">The following sample shows that a back up of filegroup(s) other than primary and memory-optimized filegroup works similar to the databases without memory-optimized tables.</span></span> <span data-ttu-id="790e3-129">Следующая команда делает резервную копию вторичной файловой группы</span><span class="sxs-lookup"><span data-stu-id="790e3-129">The following command backups up the secondary filegroup</span></span>  
  
```  
backup database imoltp filegroup='imoltp_secondary' to disk='c:\data\imoltp_secondary.dmp' with init  
```  
  
### <a name="restore"></a><span data-ttu-id="790e3-130">Восстановить</span><span class="sxs-lookup"><span data-stu-id="790e3-130">Restore</span></span>  
 <span data-ttu-id="790e3-131">В следующем примере показано, как совместно восстановить первичную файловую группу и группу, оптимизированную для памяти.</span><span class="sxs-lookup"><span data-stu-id="790e3-131">The following sample shows how to restore the primary filegroup and memory-optimized filegroup together.</span></span>  
  
```  
restore database imoltp filegroup = 'primary', filegroup = 'imoltp_mod'   
from disk='c:\data\imoltp.dmp' with partial, norecovery  
  
--restore the transaction log  
 RESTORE LOG [imoltp] FROM DISK = N'c:\data\imoltp_log.dmp' WITH  FILE = 1,  NOUNLOAD,  STATS = 10  
GO  
```  
  
 <span data-ttu-id="790e3-132">Следующий пример показывает, что восстановление файловой группы (или групп), отличной от первичной и оптимизированной для памяти файловой группы, выполняется так же, как и для баз данных без таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="790e3-132">The next sample shows that restoring filegroup(s) other than the primary and memory-optimized filegroup works similar to the databases without memory-optimized tables</span></span>  
  
```  
RESTORE DATABASE [imoltp] FILE = N'imoltp_secondary'   
FROM  DISK = N'c:\data\imoltp_secondary.dmp' WITH  FILE = 1,  RECOVERY,  NOUNLOAD,  STATS = 10  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="790e3-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="790e3-133">See Also</span></span>  
 [<span data-ttu-id="790e3-134">Резервное копирование и восстановление оптимизированных для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="790e3-134">Backup, Restore, and Recovery of Memory-Optimized Tables</span></span>](../../database-engine/backup-restore-and-recovery-of-memory-optimized-tables.md)  
  
  
