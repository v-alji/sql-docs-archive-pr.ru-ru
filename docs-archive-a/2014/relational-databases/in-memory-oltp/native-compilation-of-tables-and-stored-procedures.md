---
title: Компиляция таблиц и хранимых процедур в собственном коде | Документация Майкрософт
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5880fbd9-a23e-464a-8b44-09750eeb2dad
author: rothja
ms.author: jroth
ms.openlocfilehash: 32c5b04610d894e06278fbeecdaf3bbebe850d60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665338"
---
# <a name="native-compilation-of-tables-and-stored-procedures"></a><span data-ttu-id="8252b-102">Собственная компиляция таблиц и хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="8252b-102">Native Compilation of Tables and Stored Procedures</span></span>
  <span data-ttu-id="8252b-103">В In-Memory OLTP введено понятие компиляции в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="8252b-103">In-Memory OLTP introduces the concept of native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8252b-104">имеет возможность компиляции в собственном коде хранимых процедур, которые обращаются к оптимизированным для памяти таблицам.</span><span class="sxs-lookup"><span data-stu-id="8252b-104">can natively compile stored procedures that access memory-optimized tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8252b-105">может также скомпилировать в собственном коде оптимизированные для памяти таблицы.</span><span class="sxs-lookup"><span data-stu-id="8252b-105">is also able to natively compile memory-optimized tables.</span></span> <span data-ttu-id="8252b-106">Компиляция в собственном коде обеспечивает повышение скорости доступа к данным и более эффективное выполнение запросов по сравнению с интерпретируемыми (традиционными) командами [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8252b-106">Native compilation allows faster data access and more efficient query execution than interpreted (traditional) [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8252b-107">Компиляция таблиц и хранимых процедур в собственном коде создает библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="8252b-107">Native compilation of tables and stored procedures produce DLLs.</span></span>  
  
 <span data-ttu-id="8252b-108">Кроме того, поддерживается компиляция в собственном коде оптимизированных для памяти табличных типов.</span><span class="sxs-lookup"><span data-stu-id="8252b-108">Native compilation of memory optimized table types is also supported.</span></span> <span data-ttu-id="8252b-109">Дополнительные сведения см. в статье [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span><span class="sxs-lookup"><span data-stu-id="8252b-109">For more information, see [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span></span>  
  
 <span data-ttu-id="8252b-110">Компиляцией в собственном коде называется процесс преобразования программных конструкций в машинный код, состоящий из процессорных инструкций, без необходимости их дальнейшей компиляции или интерпретации.</span><span class="sxs-lookup"><span data-stu-id="8252b-110">Native compilation refers to the process of converting programming constructs to native code, consisting of processor instructions without the need for further compilation or interpretation.</span></span>  
  
 <span data-ttu-id="8252b-111">In-Memory OLTP компилирует оптимизированные для памяти таблицы при их создании и скомпилированные в собственном коде хранимые процедуры при их загрузке в собственные библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="8252b-111">In-Memory OLTP compiles memory-optimized tables when they are created, and natively compiled stored procedures when they are loaded to native DLLs.</span></span> <span data-ttu-id="8252b-112">Кроме того, библиотеки DLL компилируются повторно после перезапуска базы данных или сервера.</span><span class="sxs-lookup"><span data-stu-id="8252b-112">In addition, the DLLs are recompiled after a database or server restart.</span></span> <span data-ttu-id="8252b-113">Сведения, необходимые для воссоздания библиотек DLL хранятся в метаданных базы данных.</span><span class="sxs-lookup"><span data-stu-id="8252b-113">The information necessary to recreate the DLLs is stored in the database metadata.</span></span> <span data-ttu-id="8252b-114">Библиотеки DLL не являются частью базы данных, хотя они и связаны с ней.</span><span class="sxs-lookup"><span data-stu-id="8252b-114">The DLLs are not part of the database, though they are associated with the database.</span></span> <span data-ttu-id="8252b-115">Например, DLL-библиотеки не входят в резервные копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="8252b-115">For example, the DLLs are not included in database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8252b-116">Оптимизированные для памяти таблицы во время перезапуска сервера компилируются повторно.</span><span class="sxs-lookup"><span data-stu-id="8252b-116">Memory-optimized tables are recompiled during a server restart.</span></span> <span data-ttu-id="8252b-117">Чтобы ускорить восстановление данных, процедуры, скомпилированные в собственном коде, не компилируются повторно во время перезагрузки сервера, а компилируются во время первого выполнения.</span><span class="sxs-lookup"><span data-stu-id="8252b-117">To speed up database recovery, natively compiled stored procedures are not recompiled during a server restart, they are compiled at the time of first execution.</span></span> <span data-ttu-id="8252b-118">В результате этой отложенной компиляции процедуры, скомпилированные в собственном коде, отображаются только при вызове [sys.dm_os_loaded_modules (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) после первого выполнения.</span><span class="sxs-lookup"><span data-stu-id="8252b-118">As a result of this deferred compilation, natively compiled stored procedures only appear when calling [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) after first execution.</span></span>  
  
## <a name="maintenance-of-in-memory-oltp-dlls"></a><span data-ttu-id="8252b-119">Обслуживание библиотек DLL базы данных In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="8252b-119">Maintenance of In-Memory OLTP DLLs</span></span>  
 <span data-ttu-id="8252b-120">Следующий запрос отображает все библиотеки DLL таблиц и хранимых процедур, загруженных на данный момент в память сервера:</span><span class="sxs-lookup"><span data-stu-id="8252b-120">The following query shows all table and stored procedure DLLs currently loaded in memory on the server:</span></span>  
  
```sql  
SELECT name, description FROM sys.dm_os_loaded_modules  
where description = 'XTP Native DLL'  
```  
  
 <span data-ttu-id="8252b-121">Администраторам базы данных не нужно хранить файлы, созданные при компиляции в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="8252b-121">Database administrators do not need to maintain files that are generated by a native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8252b-122">автоматически удаляет созданные файлы, которые больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="8252b-122">automatically removes generated files that are no longer needed.</span></span> <span data-ttu-id="8252b-123">Например, созданные файлы будут стерты при удалении таблицы и хранимой процедуры или при удалении базы данных.</span><span class="sxs-lookup"><span data-stu-id="8252b-123">For example, generated files will be deleted when a table and stored procedure is deleted, or if a database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8252b-124">Если компиляция была прервана или завершилась ошибкой, то некоторые сформированные файлы не будут удалены.</span><span class="sxs-lookup"><span data-stu-id="8252b-124">If compilation fails or is interrupted, some generated files are not removed.</span></span> <span data-ttu-id="8252b-125">Эти файлы оставляются специально для целей поддержки и будут удалены при удалении базы данных.</span><span class="sxs-lookup"><span data-stu-id="8252b-125">These files are intentionally left behind for supportability and are removed when the database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8252b-126">Во время запуска базы данных SQL Server компилирует библиотеки DLL для всех таблиц, необходимых для восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="8252b-126">During database startup, SQL Server compiles DLLs for all tables needed for database recovery.</span></span> <span data-ttu-id="8252b-127">Если таблица была удалена непосредственно до перезапуска базы данных, остатки таблицы все еще могут оставаться в файлах контрольных точек или журнале транзакций для того, чтобы библиотеки DLL для таблицы можно было перекомпилировать во время запуска базы данных.</span><span class="sxs-lookup"><span data-stu-id="8252b-127">If a table was dropped just prior to a database restart there can still be remnants of the table in the checkpoint files or the transaction log so the DLL for the table might be recompiled during database startup.</span></span> <span data-ttu-id="8252b-128">После перезагрузки компьютера библиотека DLL будет выгружена и удалена в процессе обычной очистки.</span><span class="sxs-lookup"><span data-stu-id="8252b-128">After restart the DLL will be unloaded and the files will be removed by the normal cleanup process.</span></span>  
  
## <a name="native-compilation-of-tables"></a><span data-ttu-id="8252b-129">Компиляция таблиц в собственном коде</span><span class="sxs-lookup"><span data-stu-id="8252b-129">Native Compilation of Tables</span></span>  
 <span data-ttu-id="8252b-130">Создание оптимизированной для памяти таблицы с помощью инструкции `CREATE TABLE` приводит к тому, что табличные данные записываются в метаданные базы данных, а в памяти создаются структуры таблиц и индексов.</span><span class="sxs-lookup"><span data-stu-id="8252b-130">Creating a memory-optimized table using the `CREATE TABLE` statement results in the table information being written to the database metadata and the table and index structures created in memory.</span></span> <span data-ttu-id="8252b-131">Таблица также будет скомпилирована в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="8252b-131">The table will also be compiled to a DLL.</span></span>  
  
 <span data-ttu-id="8252b-132">Рассмотрим следующий пример скрипта, который создает базу данных и оптимизированную для памяти таблицу:</span><span class="sxs-lookup"><span data-stu-id="8252b-132">Consider the following sample script, which creates a database and a memory-optimized table:</span></span>  
  
```sql  
use master  
go  
create database db1  
go  
alter database db1 add filegroup db1_mod contains memory_optimized_data  
go  
-- adapt filename as needed  
alter database db1 add file (name='db1_mod', filename='c:\data\db1_mod') to filegroup db1_mod  
go  
use db1  
go  
create table dbo.t1  
   (c1 int not null primary key nonclustered,  
    c2 INT)  
with (memory_optimized=on)  
go  
-- retrieve the path of the DLL for table t1  
select name, description FROM sys.dm_os_loaded_modules  
where name like '%xtp_t_' + cast(db_id() as varchar(10)) + '_' + cast(object_id('dbo.t1') as varchar(10)) + '.dll'  
go  
```  
  
 <span data-ttu-id="8252b-133">При создании таблицы также формируется и загружается в память библиотека DLL таблицы.</span><span class="sxs-lookup"><span data-stu-id="8252b-133">Creating the table also creates the table DLL and loads the DLL in memory.</span></span> <span data-ttu-id="8252b-134">Запрос динамического административного представления сразу после выполнения инструкции CREATE TABLE возвращает путь к библиотеке DLL таблицы.</span><span class="sxs-lookup"><span data-stu-id="8252b-134">The DMV query immediately after the CREATE TABLE statement retrieves the path of the table DLL.</span></span>  
  
 <span data-ttu-id="8252b-135">Библиотека DLL таблицы понимает структуры индекса и формат строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="8252b-135">The table DLL understands the index structures and row format of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8252b-136">использует библиотеку DLL для просмотра индексов, получения строк, а также хранения содержимого строк.</span><span class="sxs-lookup"><span data-stu-id="8252b-136">uses the DLL for traversing indexes, retrieving rows, as well as storing the contents of the rows.</span></span>  
  
## <a name="native-compilation-of-stored-procedures"></a><span data-ttu-id="8252b-137">Компиляция хранимых процедур в собственном коде</span><span class="sxs-lookup"><span data-stu-id="8252b-137">Native Compilation of Stored Procedures</span></span>  
 <span data-ttu-id="8252b-138">Хранимые процедуры, которые отмечены как NATIVE_COMPILATION, компилируются в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="8252b-138">Stored procedures that are marked with NATIVE_COMPILATION are natively compiled.</span></span> <span data-ttu-id="8252b-139">Это означает, что все инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] в процедуре компилируются в машинный код для эффективного выполнения бизнес-логики, критической с точки зрения производительности.</span><span class="sxs-lookup"><span data-stu-id="8252b-139">This means the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure are all compiled to native code for efficient execution of performance-critical business logic.</span></span>  
  
 <span data-ttu-id="8252b-140">Дополнительные сведения о скомпилированных в собственном коде хранимых процедурах см. в разделе [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8252b-140">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="8252b-141">Рассмотрим следующий пример хранимой процедуры, которая вставляет строки в таблицу t1 из предыдущего примера:</span><span class="sxs-lookup"><span data-stu-id="8252b-141">Consider the following sample stored procedure, which inserts rows in the table t1 from the previous example:</span></span>  
  
```sql  
create procedure dbo.native_sp  
with native_compilation, schemabinding, execute as owner  
as  
begin atomic  
with (transaction isolation level=snapshot, language=N'us_english')  
  
  declare @i int = 1000000  
  while @i > 0  
  begin  
    insert dbo.t1 values (@i, @i+1)  
    set @i -= 1  
  end  
  
end  
go  
exec dbo.native_sp  
go  
-- reset  
delete from dbo.t1  
go  
```  
  
 <span data-ttu-id="8252b-142">Библиотека DLL для native_sp может напрямую взаимодействовать с библиотекой DLL для t1, а также c подсистемой хранилища In-Memory OLTP, чтобы вставлять строки с максимально возможной скоростью.</span><span class="sxs-lookup"><span data-stu-id="8252b-142">The DLL for native_sp can interact directly with the DLL for t1, as well as the In-Memory OLTP storage engine, to insert the rows as fast as possible.</span></span>  
  
 <span data-ttu-id="8252b-143">Компилятор In-Memory OLTP использует оптимизатор запросов для создания эффективного плана выполнения для каждого из запросов в хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="8252b-143">The In-Memory OLTP compiler leverages the query optimizer to create an efficient execution plan for each of the queries in the stored procedure.</span></span> <span data-ttu-id="8252b-144">Обратите внимание, что скомпилированные в собственном коде хранимые процедуры не перекомпилируются автоматически при изменении данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="8252b-144">Note that natively compiled stored procedures are not automatically recompiled if the data in the table changes.</span></span> <span data-ttu-id="8252b-145">Дополнительные сведения о сборе статистики и хранимых процедурах в In-Memory OLTP см. в разделе [Статистика для таблиц, оптимизированных для памяти](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8252b-145">For more information on maintaining statistics and stored procedures with In-Memory OLTP see [Statistics for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="security-considerations-for-native-compilation"></a><span data-ttu-id="8252b-146">Вопросы безопасности для компиляции в собственном коде</span><span class="sxs-lookup"><span data-stu-id="8252b-146">Security Considerations for Native Compilation</span></span>  
 <span data-ttu-id="8252b-147">Компиляция в собственном коде таблиц и хранимых процедур использует компилятор In-Memory OLTP.</span><span class="sxs-lookup"><span data-stu-id="8252b-147">Native compilation of tables and stored procedures uses the In-Memory OLTP compiler.</span></span> <span data-ttu-id="8252b-148">Этот компилятор создает файлы, которые записываются на диск и загружаются в память.</span><span class="sxs-lookup"><span data-stu-id="8252b-148">This compiler produces files that are written to disk and loaded into memory.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8252b-149">использует следующие механизмы для ограничения доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="8252b-149">uses the following mechanisms to limit access to these files.</span></span>  
  
### <a name="native-compiler"></a><span data-ttu-id="8252b-150">Собственный компилятор</span><span class="sxs-lookup"><span data-stu-id="8252b-150">Native Compiler</span></span>  
 <span data-ttu-id="8252b-151">Исполняемый файл компилятора, а также двоичные файлы и файлы заголовков, необходимые для компиляции в собственном коде, устанавливаются как часть экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в папке MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="8252b-151">The compiler executable, as well as binaries and header files required for native compilation are installed as part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance under the folder MSSQL\Binn\Xtp.</span></span> <span data-ttu-id="8252b-152">Таким образом, если экземпляр по умолчанию установлен в папке c:\Program Files, файлы компилятора устанавливаются в папку c:\Program Files \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. мссклсервер\мсскл\бинн\кстп.</span><span class="sxs-lookup"><span data-stu-id="8252b-152">So, if the default instance is installed under C:\Program Files, the compiler files are installed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\Binn\Xtp.</span></span>  
  
 <span data-ttu-id="8252b-153">Чтобы ограничить доступ к компилятору, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует списки управления доступом (ACL), ограничивающие доступ к двоичным файлам.</span><span class="sxs-lookup"><span data-stu-id="8252b-153">To limit access to the compiler, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses access control lists (ACLs) to restrict access to binary files.</span></span> <span data-ttu-id="8252b-154">Все двоичные файлы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] защищены от изменения и несанкционированного доступа через списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="8252b-154">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries are protected against modification or tampering through ACLs.</span></span> <span data-ttu-id="8252b-155">Списки управления доступом собственного компилятора также ограничивают использование компилятора; только учетная запись службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и администраторы имеют разрешения на чтение и выполнение для файлов собственного компилятора.</span><span class="sxs-lookup"><span data-stu-id="8252b-155">The native compiler's ACLs also limit use of the compiler; only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators have read and execute permissions for native compiler files.</span></span>  
  
### <a name="files-generated-by-a-native-compilation"></a><span data-ttu-id="8252b-156">Файлы, созданные компиляцией в собственном коде</span><span class="sxs-lookup"><span data-stu-id="8252b-156">Files Generated by a Native Compilation</span></span>  
 <span data-ttu-id="8252b-157">Файлы, создаваемые при компиляции таблицы хранимой процедуры, включают DLL и промежуточные файлы, в том числе файлы со следующими расширениями: C, OBJ, XML и PDB.</span><span class="sxs-lookup"><span data-stu-id="8252b-157">The files produced when a table or stored procedure is compiled include the DLL and intermediate files including files with the following extensions: .c, .obj, .xml, and .pdb.</span></span> <span data-ttu-id="8252b-158">Созданные файлы сохраняются во вложенной папке папки данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8252b-158">The generated files are saved in a subfolder of the default data folder.</span></span> <span data-ttu-id="8252b-159">Вложенная папка называется Xtp.</span><span class="sxs-lookup"><span data-stu-id="8252b-159">The subfolder is called Xtp.</span></span> <span data-ttu-id="8252b-160">При установке экземпляра по умолчанию с папкой данных по умолчанию созданные файлы помещаются в папку C:\Program Files \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. мссклсервер\мсскл\дата\кстп.</span><span class="sxs-lookup"><span data-stu-id="8252b-160">When installing the default instance with the default data folder, the generated files are placed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\DATA\Xtp.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8252b-161">предотвращает изменение создаваемых библиотек DLL тремя способами.</span><span class="sxs-lookup"><span data-stu-id="8252b-161">prevents tampering with the generated DLLs in three ways:</span></span>  
  
-   <span data-ttu-id="8252b-162">Если таблица или хранимая процедура компилируется в DLL, эта DLL немедленно загружается в память и связывается с процессом sqlserver.exe.</span><span class="sxs-lookup"><span data-stu-id="8252b-162">When a table or stored procedure is compiled to a DLL, this DLL is immediately loaded into memory and linked to the sqlserver.exe process.</span></span> <span data-ttu-id="8252b-163">Библиотеку DLL нельзя изменить, если она связана с процессом.</span><span class="sxs-lookup"><span data-stu-id="8252b-163">A DLL cannot be modified while it is linked to a process.</span></span>  
  
-   <span data-ttu-id="8252b-164">При перезапуске базы данных перекомпилируются все таблицы и хранимые процедуры (удаленные и воссозданные) на основе метаданных базы данных.</span><span class="sxs-lookup"><span data-stu-id="8252b-164">When a database is restarted, all tables and stored procedures are recompiled (removed and recreated) based on the database metadata.</span></span> <span data-ttu-id="8252b-165">При этом удаляются все изменения, внесенные в созданный файл вредоносным агентом.</span><span class="sxs-lookup"><span data-stu-id="8252b-165">This will remove any changes made to a generated file by a malicious agent.</span></span>  
  
-   <span data-ttu-id="8252b-166">Созданные файлы считаются частью пользовательских данных и имеют те же ограничения безопасности через списки ACL, что и файлы базы данных: только учетная запись службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и системные администраторы имеют доступ к этим файлам.</span><span class="sxs-lookup"><span data-stu-id="8252b-166">The generated files are considered part of user data, and have the same security restrictions, via ACLs, as database files: only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators can access these files.</span></span>  
  
 <span data-ttu-id="8252b-167">Взаимодействие с пользователем для управления этими файлами не требуется.</span><span class="sxs-lookup"><span data-stu-id="8252b-167">No user interaction is needed to manage these files.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8252b-168">создает и удаляет файлы по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="8252b-168">will create and remove the files as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8252b-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="8252b-169">See Also</span></span>  
 <span data-ttu-id="8252b-170">[Оптимизированные для памяти таблицы](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="8252b-170">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="8252b-171">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="8252b-171">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
