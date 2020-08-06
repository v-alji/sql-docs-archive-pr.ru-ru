---
title: Мониторинг и устранение неполадок с использованием памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 7a458b9c-3423-4e24-823d-99573544c877
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5805ed06ad78040dbdf6c8557e5f548ad57f618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750976"
---
# <a name="monitor-and-troubleshoot-memory-usage"></a><span data-ttu-id="dae31-102">Мониторинг и устранение неполадок с использованием памяти</span><span class="sxs-lookup"><span data-stu-id="dae31-102">Monitor and Troubleshoot Memory Usage</span></span>
  [!INCLUDE[hek_1](../../includes/hek-1-md.md)] <span data-ttu-id="dae31-103">использует память в шаблонах, отличных от дисковых таблиц.</span><span class="sxs-lookup"><span data-stu-id="dae31-103">consumes memory in different patterns than disk-based tables.</span></span> <span data-ttu-id="dae31-104">Можно контролировать объем выделенной памяти, используемый оптимизированными для памяти таблицами и индексами в базе данных, с помощью динамических административных представлений (DMV) и счетчиков производительности, предназначенных для подсистемы памяти и сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="dae31-104">You can monitor the amount of memory allocated and used by memory-optimized tables and indexes in your database using the DMVs or performance counters provided for memory and the garbage collection subsystem.</span></span>  <span data-ttu-id="dae31-105">Это обеспечивает видимость на уровне системы и базы данных и позволяет предотвращать проблемы нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-105">This gives you visibility at both the system and database level and lets you prevent problems due to memory exhaustion.</span></span>

 <span data-ttu-id="dae31-106">В этом разделе описывается процесс мониторинга использования памяти в [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae31-106">This topic covers monitoring your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] memory usage.</span></span>


##  <a name="create-a-sample-database-with-memory-optimized-tables"></a><a name="bkmk_CreateDB"></a> <span data-ttu-id="dae31-107">Создание образца базы данных с таблицами, оптимизированными для памяти</span><span class="sxs-lookup"><span data-stu-id="dae31-107">Create a sample database with memory-optimized tables</span></span>
 <span data-ttu-id="dae31-108">Этот подраздел можно пропустить, если у вас уже есть база данных с таблицами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-108">You can skip this section if you already have a database with memory-optimized tables.</span></span>

 <span data-ttu-id="dae31-109">Следующие действия создадут базу данных с тремя оптимизированными для памяти таблицами, которые можно использовать в оставшейся части этого раздела.</span><span class="sxs-lookup"><span data-stu-id="dae31-109">The following steps create a database with three memory-optimized tables that you can use in the remainder of this topic.</span></span> <span data-ttu-id="dae31-110">В примере мы сопоставили базы данных с пулом ресурсов, что позволит управлять объемом памяти, который может быть занят таблицами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-110">In the example, we mapped the database to a resource pool so that we can control how much memory can be taken by memory-optimized tables.</span></span>

1.  <span data-ttu-id="dae31-111">Запустите среду [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dae31-111">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>

2.  <span data-ttu-id="dae31-112">Нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="dae31-112">Click **New Query**.</span></span>

3.  <span data-ttu-id="dae31-113">Вставьте этот код в окно нового запроса и выполните каждый раздел.</span><span class="sxs-lookup"><span data-stu-id="dae31-113">Paste this code into the new query window and execute each section.</span></span>

    ```
    -- create a database to be used
    CREATE DATABASE IMOLTP_DB
    GO

    ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_xtp_fg CONTAINS MEMORY_OPTIMIZED_DATA
    ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_xtp' , FILENAME = 'C:\Data\IMOLTP_DB_xtp') TO FILEGROUP IMOLTP_DB_xtp_fg;
    GO

    USE IMOLTP_DB
    GO

    -- create the resoure pool
    CREATE RESOURCE POOL PoolIMOLTP WITH (MAX_MEMORY_PERCENT = 60);
    ALTER RESOURCE GOVERNOR RECONFIGURE;
    GO

    -- bind the database to a resource pool
    EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'PoolIMOLTP'

    -- you can query the binding using the catalog view as described here
    SELECT d.database_id
         , d.name
         , d.resource_pool_id
    FROM sys.databases d
    GO

    -- take database offline/online to finalize the binding to the resource pool
    USE master
    GO

    ALTER DATABASE IMOLTP_DB SET OFFLINE
    GO
    ALTER DATABASE IMOLTP_DB SET ONLINE
    GO

    -- create some tables
    USE IMOLTP_DB
    GO

    -- create table t1
    CREATE TABLE dbo.t1 (
           c1 int NOT NULL CONSTRAINT [pk_t1_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- load t1 150K rows
    DECLARE @i int = 0
    BEGIN TRAN
    WHILE (@i <= 150000)
       BEGIN
          INSERT t1 VALUES (@i, 'a', replicate ('b', 8000))
          SET @i += 1;
       END
    Commit
    GO

    -- Create another table, t2
    CREATE TABLE dbo.t2 (
           c1 int NOT NULL CONSTRAINT [pk_t2_c1] PRIMARY KEY NONCLUSTERED
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO

    -- Create another table, t3 
    CREATE TABLE dbo.t3 (
           c1 int NOT NULL CONSTRAINT [pk_t3_c1] PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 1000000)
         , c2 char(40) NOT NULL
         , c3 char(8000) NOT NULL
         ) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)
    GO
    ```

##  <a name="monitoring-memory-usage"></a><span data-ttu-id="dae31-114">Наблюдение за использованием памяти</span><span class="sxs-lookup"><span data-stu-id="dae31-114">Monitoring Memory Usage</span></span>

###  <a name="using-ssmanstudiofull"></a><span data-ttu-id="dae31-115">Использование [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dae31-115">Using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>
 [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="dae31-116">поставляется вместе со встроенными стандартными отчетами для наблюдения за объемом памяти, используемым таблицами, хранимыми в памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-116">ships with built-in standard reports to monitor the memory consumed by in-memory tables.</span></span> <span data-ttu-id="dae31-117">Доступ к этим отчетам можно получить с помощью обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="dae31-117">You can access these reports using Object Explorer.</span></span> <span data-ttu-id="dae31-118">Обозреватель объектов также можно использовать для контроля памяти, занятой отдельными таблицами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-118">You can also use the object explorer to monitor memory consumed by individual memory-optimized tables.</span></span>

#### <a name="consumption-at-the-database-level"></a><span data-ttu-id="dae31-119">Использование на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="dae31-119">Consumption at the database level</span></span>
 <span data-ttu-id="dae31-120">Можно отслеживать использование памяти на уровне базы данных следующим образом.</span><span class="sxs-lookup"><span data-stu-id="dae31-120">You can monitor memory use at the database level as follows.</span></span>

1.  <span data-ttu-id="dae31-121">Запустите среду [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] и подключитесь к серверу.</span><span class="sxs-lookup"><span data-stu-id="dae31-121">Launch [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and connect to a server.</span></span>

2.  <span data-ttu-id="dae31-122">В обозревателе объектов щелкните правой кнопкой мыши базу данных, по которой нужно получить отчеты.</span><span class="sxs-lookup"><span data-stu-id="dae31-122">In Object Explorer, right-click the database you want reports on.</span></span>

3.  <span data-ttu-id="dae31-123">В контекстном меню выберите **Отчеты** -> **Стандартные отчеты** -> **Использование памяти таблицами, оптимизированными для памяти**</span><span class="sxs-lookup"><span data-stu-id="dae31-123">In the context menu select, **Reports** -> **Standard Reports** -> **Memory Usage By Memory Optimized Objects**</span></span>

 <span data-ttu-id="dae31-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="dae31-124">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuse.gif "HK_MM_SSMS")</span></span>

 <span data-ttu-id="dae31-125">Данный отчет показывает потребление памяти базой данных, созданной ранее.</span><span class="sxs-lookup"><span data-stu-id="dae31-125">This report shows memory consumption by the database we created above.</span></span>

 <span data-ttu-id="dae31-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span><span class="sxs-lookup"><span data-stu-id="dae31-126">![HK_MM_SSMS](../../database-engine/media/hk-mm-ssms-stdrpt-memuserpt.gif "HK_MM_SSMS")</span></span>

###  <a name="using-dmvs"></a><span data-ttu-id="dae31-127">Использование представлений DMV</span><span class="sxs-lookup"><span data-stu-id="dae31-127">Using DMVs</span></span>
 <span data-ttu-id="dae31-128">Существует несколько динамических административных представлений для контроля объема памяти, используемого оптимизированными для памяти таблицами, индексами, системными объектами и структурами времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="dae31-128">There are a number of DMVs available to monitor memory consumed by memory-optimized tables, indexes, system objects, and by run-time structures.</span></span>

#### <a name="memory-consumption-by-memory-optimized-tables-and-indexes"></a><span data-ttu-id="dae31-129">Использование памяти оптимизированными для памяти таблицами и индексами</span><span class="sxs-lookup"><span data-stu-id="dae31-129">Memory consumption by memory-optimized tables and indexes</span></span>
 <span data-ttu-id="dae31-130">Можно узнать использование памяти для всех пользовательских таблиц, индексов и системных объектов с помощью запроса `sys.dm_db_xtp_table_memory_stats` , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dae31-130">You can find memory consumption for all user tables, indexes, and system objects by querying `sys.dm_db_xtp_table_memory_stats` as shown here.</span></span>

```sql
SELECT object_name(object_id) AS Name
     , *
   FROM sys.dm_db_xtp_table_memory_stats
```

 <span data-ttu-id="dae31-131">**Образец вывода**</span><span class="sxs-lookup"><span data-stu-id="dae31-131">**Sample Output**</span></span>

```
Name       object_id   memory_allocated_for_table_kb memory_used_by_table_kb memory_allocated_for_indexes_kb memory_used_by_indexes_kb
---------- ----------- ----------------------------- ----------------------- ------------------------------- -------------------------
t3         629577281   0                             0                       128                             0
t1         565577053   1372928                       1200008                 7872                            1942
t2         597577167   0                             0                       128                             0
NULL       -6          0                             0                       2                               2
NULL       -5          0                             0                       24                              24
NULL       -4          0                             0                       2                               2
NULL       -3          0                             0                       2                               2
NULL       -2          192                           25                      16                              16
```

 <span data-ttu-id="dae31-132">Дополнительные сведения см. в разделе [sys. dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span><span class="sxs-lookup"><span data-stu-id="dae31-132">For more information, see [sys.dm_db_xtp_table_memory_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql?view=sql-server-2016).</span></span>

#### <a name="memory-consumption-by-internal-system-structures"></a><span data-ttu-id="dae31-133">Использование памяти внутренними системными структурами</span><span class="sxs-lookup"><span data-stu-id="dae31-133">Memory consumption by internal system structures</span></span>
 <span data-ttu-id="dae31-134">Память также используется системными объектами, например транзакционными структурами, буферами для разностных файлов и данных, структурами для сборки мусора и другими объектами.</span><span class="sxs-lookup"><span data-stu-id="dae31-134">Memory is also consumed by system objects, such as, transactional structures, buffers for data and delta files, garbage collection structures, and more.</span></span> <span data-ttu-id="dae31-135">Можно узнать объем памяти, используемый для этих системных объектов с помощью запроса `sys.dm_xtp_system_memory_consumers` , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dae31-135">You can find the memory used for these system objects by querying `sys.dm_xtp_system_memory_consumers` as shown here.</span></span>

```sql
SELECT memory_consumer_desc
     , allocated_bytes/1024 AS allocated_bytes_kb
     , used_bytes/1024 AS used_bytes_kb
     , allocation_count
   FROM sys.dm_xtp_system_memory_consumers
```

 <span data-ttu-id="dae31-136">**Образец вывода**</span><span class="sxs-lookup"><span data-stu-id="dae31-136">**Sample Output**</span></span>

```
memory_consumer_ desc allocated_bytes_kb   used_bytes_kb        allocation_count
------------------------- -------------------- -------------------- ----------------
VARHEAP                   0                    0                    0
VARHEAP                   384                  0                    0
DBG_GC_OUTSTANDING_T      64                   64                   910
ACTIVE_TX_MAP_LOOKAS      0                    0                    0
RECOVERY_TABLE_CACHE      0                    0                    0
RECENTLY_USED_ROWS_L      192                  192                  261
RANGE_CURSOR_LOOKSID      0                    0                    0
HASH_CURSOR_LOOKASID      128                  128                  455
SAVEPOINT_LOOKASIDE       0                    0                    0
PARTIAL_INSERT_SET_L      192                  192                  351
CONSTRAINT_SET_LOOKA      192                  192                  646
SAVEPOINT_SET_LOOKAS      0                    0                    0
WRITE_SET_LOOKASIDE       192                  192                  183
SCAN_SET_LOOKASIDE        64                   64                   31
READ_SET_LOOKASIDE        0                    0                    0
TRANSACTION_LOOKASID      448                  448                  156
PGPOOL:256K               768                  768                  3
PGPOOL: 64K               0                    0                    0
PGPOOL:  4K               0                    0                    0
```

 <span data-ttu-id="dae31-137">Дополнительные сведения см. в статье [sys.dm_xtp_system_memory_consumers (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dae31-137">For more information see [sys.dm_xtp_system_memory_consumers &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-table-memory-stats-transact-sql).</span></span>


#### <a name="memory-consumption-at-run-time-when-accessing-memory-optimized-tables"></a><span data-ttu-id="dae31-138">Использование памяти во время выполнения при обращении к оптимизированным для памяти таблицам</span><span class="sxs-lookup"><span data-stu-id="dae31-138">Memory consumption at run-time when accessing memory-optimized tables</span></span>
 <span data-ttu-id="dae31-139">Следующим запросом можно определить объем памяти, занятый структурами времени выполнения, например для кэша процедур. Выполните этот запрос, чтобы получить объем памяти, используемый структурами времени выполнения, например для кэша процедур.</span><span class="sxs-lookup"><span data-stu-id="dae31-139">You can determine the memory consumed by run time structures, such as the procedure cache with the following query: run this query to get the memory used by run-time structures such as for the procedure cache.</span></span> <span data-ttu-id="dae31-140">Все структуры времени помечены как XTP.</span><span class="sxs-lookup"><span data-stu-id="dae31-140">All run-time structures are tagged with XTP.</span></span>

```sql
SELECT memory_object_address
     , pages_in_bytes
     , bytes_used
     , type
   FROM sys.dm_os_memory_objects WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="dae31-141">**Образец вывода**</span><span class="sxs-lookup"><span data-stu-id="dae31-141">**Sample Output**</span></span>

```
memory_object_address pages_ in_bytes bytes_used type
--------------------- ------------------- ---------- ----
0x00000001F1EA8040    507904              NULL       MEMOBJ_XTPDB
0x00000001F1EAA040    68337664            NULL       MEMOBJ_XTPDB
0x00000001FD67A040    16384               NULL       MEMOBJ_XTPPROCCACHE
0x00000001FD68C040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD284040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD302040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD382040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD402040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD482040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD502040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001FD67E040    16384               NULL       MEMOBJ_XTPPROCPARTITIONEDHEAP
0x00000001F813C040    8192                NULL       MEMOBJ_XTPBLOCKALLOC
0x00000001F813E040    16842752            NULL       MEMOBJ_XTPBLOCKALLOC
```

 <span data-ttu-id="dae31-142">Дополнительные сведения см. в разделе [sys. dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dae31-142">For more information, see [sys.dm_os_memory_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-objects-transact-sql).</span></span>

#### <a name="memory-consumed-by-hek_2-engine-across-the-instance"></a><span data-ttu-id="dae31-143">Память, используемая модулем [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] в памяти в пределах экземпляра</span><span class="sxs-lookup"><span data-stu-id="dae31-143">Memory consumed by [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine across the instance</span></span>
 <span data-ttu-id="dae31-144">В экземпляре SQL Server память, выделенная для модуля [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] в памяти и оптимизированных для памяти объектов, управляется таким же образом, как и любой другой потребитель памяти в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae31-144">Memory allocated to the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine and the memory-optimized objects is managed the same way as any other memory consumer within a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="dae31-145">Клерки типа учетных записей MEMORYCLERK_XTP для всей памяти, выделенной для модуля [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae31-145">The clerks of type MEMORYCLERK_XTP accounts for all the memory allocated to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span> <span data-ttu-id="dae31-146">Следующий запрос применяется для вычисления объема всей памяти, используемого модулем [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae31-146">Use the following query to find all the memory used by the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine.</span></span>

```sql
-- this DMV accounts for all memory used by the hek_2 engine
SELECT type
     , name
     , memory_node_id
     , pages_kb/1024 AS pages_MB 
   FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'
```

 <span data-ttu-id="dae31-147">Следующий образец вывода показывает, что общий объем выделенной памяти из потребления памяти на уровне системы равен 18 МБ, а 1358 МБ выделено базе данных с идентификатором 5.</span><span class="sxs-lookup"><span data-stu-id="dae31-147">The sample output shows that the total memory allocated is 18 MB system-level memory consumption and 1358MB allocated to database id of 5.</span></span> <span data-ttu-id="dae31-148">Поскольку эта база данных сопоставлена с выделенным пулом ресурсов, то эта память учитывается в данном пуле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dae31-148">Since this database is mapped to a dedicated resource pool, this memory is accounted for in that resource pool.</span></span>

 <span data-ttu-id="dae31-149">**Образец вывода**</span><span class="sxs-lookup"><span data-stu-id="dae31-149">**Sample Output**</span></span>

```
type                 name       memory_node_id pages_MB
-------------------- ---------- -------------- --------------------
MEMORYCLERK_XTP      Default    0              18
MEMORYCLERK_XTP      DB_ID_5    0              1358
MEMORYCLERK_XTP      Default    64             0
```

 <span data-ttu-id="dae31-150">Дополнительные сведения см. в разделе [sys. dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dae31-150">For more information, see [sys.dm_os_memory_clerks (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-memory-clerks-transact-sql).</span></span>

##   <a name="managing-memory-consumed-by-memory-optimized-objects"></a><span data-ttu-id="dae31-151">Управление памятью, занятой объектами, оптимизированными для памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-151">Managing memory consumed by memory-optimized objects</span></span>
 <span data-ttu-id="dae31-152">Можно управлять общим объемом памяти, используемым оптимизированными для памяти таблицами, привязав его к указанным пулом ресурсам, как описано в статье [Привязка базы данных с таблицами, оптимизированными для памяти, к пулу ресурсов](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="dae31-152">You can control the total memory consumed by memory-optimized tables by binding it to a named resource pool as described in the topic [Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md).</span></span>

##  <a name="troubleshooting-memory-issues"></a><span data-ttu-id="dae31-153">Устранение неполадок с памятью</span><span class="sxs-lookup"><span data-stu-id="dae31-153">Troubleshooting Memory Issues</span></span>
 <span data-ttu-id="dae31-154">Диагностика проблем памяти в процессе из трех действий.</span><span class="sxs-lookup"><span data-stu-id="dae31-154">Troubleshooting memory issues is a three step process:</span></span>

1.  <span data-ttu-id="dae31-155">Определите, сколько памяти используется объектами в вашей базе данных или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="dae31-155">Identify how much memory is being consumed by the objects in your database or instance.</span></span> <span data-ttu-id="dae31-156">Можно использовать широкий набор средств наблюдения, доступных для таблиц, оптимизированных для памяти, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="dae31-156">You can use a rich set of monitoring tools available for memory-optimized tables as described earlier.</span></span>  <span data-ttu-id="dae31-157">Например, представление DMV `sys.dm_db_xtp_table_memory_stats` или `sys.dm_os_memory_clerks`.</span><span class="sxs-lookup"><span data-stu-id="dae31-157">For example the DMVs `sys.dm_db_xtp_table_memory_stats` or `sys.dm_os_memory_clerks`.</span></span>

2.  <span data-ttu-id="dae31-158">Определите, как растет потребление памяти и сколько места для маневра вам останется.</span><span class="sxs-lookup"><span data-stu-id="dae31-158">Determine how memory consumption is growing and how much head room you have left.</span></span> <span data-ttu-id="dae31-159">Периодически наблюдая за использованием памяти, вы узнаете, как растет использование памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-159">By monitoring the memory consumption periodically, you can know how the memory use is growing.</span></span> <span data-ttu-id="dae31-160">Например, если база данных сопоставлена с именованным пулом ресурсов, можно понаблюдать за счетчиком использованной памяти (в КБ), чтобы оценить, как растет потребление памяти.</span><span class="sxs-lookup"><span data-stu-id="dae31-160">For example, if you have mapped the database to a named resource pool, you can monitor the performance counter Used Memory (KB) to see how memory usage is growing.</span></span>

3.  <span data-ttu-id="dae31-161">Примите меры, чтобы избежать потенциальных проблем с памятью.</span><span class="sxs-lookup"><span data-stu-id="dae31-161">Take action to mitigate the potential memory issues.</span></span> <span data-ttu-id="dae31-162">Дополнительные сведения см. в разделе [Устранение проблем нехватки памяти](resolve-out-of-memory-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dae31-162">For more information, see [Resolve Out Of Memory Issues](resolve-out-of-memory-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dae31-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="dae31-163">See Also</span></span>
 <span data-ttu-id="dae31-164">[Привязка базы данных с таблицами, оптимизированными для памяти, к изменениям пула ресурсов](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [MIN_MEMORY_PERCENT и max_memory_percent в существующем пуле](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span><span class="sxs-lookup"><span data-stu-id="dae31-164">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) [Change MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on an existing pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md#change-min-memory-percent-and-max-memory-percent-on-an-existing-pool)</span></span>


