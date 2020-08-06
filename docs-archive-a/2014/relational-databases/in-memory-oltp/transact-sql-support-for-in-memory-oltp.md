---
title: Поддержка Transact-SQL для выполняющейся в памяти OLTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b1cc7c30-1747-4c21-88ac-e95a5e58baac
author: rothja
ms.author: jroth
ms.openlocfilehash: bf3708a258e3bb97231e45b10bea2c59351a06a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749875"
---
# <a name="transact-sql-support-for-in-memory-oltp"></a><span data-ttu-id="a639b-102">Поддержка Transact-SQL для In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="a639b-102">Transact-SQL Support for In-Memory OLTP</span></span>
  <span data-ttu-id="a639b-103">Доступ к оптимизированным для памяти таблицам можно получить с помощью любого запроса Transact-SQL или операции DML (SELECT, INSERT, UPDATE или DELETE), нерегламентированных пакетов и модулей SQL, таких как хранимые процедуры, функции, возвращающие табличное значение, триггеры и представления.</span><span class="sxs-lookup"><span data-stu-id="a639b-103">You can access memory-optimized tables using any Transact-SQL query or DML statement (SELECT, INSERT, UPDATE, or DELETE), ad hoc statement, and SQL module such as stored procedures, table-value functions, scalar functions, triggers, and views.</span></span> <span data-ttu-id="a639b-104">Дополнительные сведения см. в разделе [доступ к оптимизированным для памяти таблицам с использованием интерпретированного языка Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a639b-104">For more information see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span>  
  
 <span data-ttu-id="a639b-105">Хранимые процедуры, которые ссылаются только на оптимизированные для памяти таблицы, могут быть скомпилированы в собственном коде и обычно предоставляют значительное повышение производительности по сравнению с интерпретируемыми хранимыми процедурами (на базе диска).</span><span class="sxs-lookup"><span data-stu-id="a639b-105">Stored procedures that only reference memory-optimized tables can be natively compiled into machine code and typically provide significant performance gains over interpreted (disk-based) stored procedures.</span></span> <span data-ttu-id="a639b-106">Для оптимизации доступа к таблицам, оптимизированным для памяти, используйте хранимые процедуры, скомпилированные в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="a639b-106">For optimized access to memory-optimized tables use natively compiled stored procedures.</span></span> <span data-ttu-id="a639b-107">Дополнительные сведения см. в статье [Хранимые процедуры, скомпилированные в собственном коде](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a639b-107">For more information, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="a639b-108">При создании и изменении объектов базы данных (инструкций DDL) были изменены следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="a639b-108">When creating and modifying database objects (DDL statements), the following statements have been modified:</span></span>  
  
-   <span data-ttu-id="a639b-109">[Параметры Alter Database File и Filegroup &#40;&#41;Transact-SQL](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (см. `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="a639b-109">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="a639b-110">[Создание &#40;базы данных SQL Server&#41;Transact-SQL](/sql/t-sql/statements/create-database-sql-server-transact-sql) (см. `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="a639b-110">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="a639b-111">[CREATE PROCEDURE &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-procedure-transact-sql) (см. `NATIVE_COMPILATION` ,, `SCHEMABINDING` `EXECUTE AS` и `BEGIN ATOMIC` ).</span><span class="sxs-lookup"><span data-stu-id="a639b-111">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (see `NATIVE_COMPILATION`, `SCHEMABINDING`, `EXECUTE AS`, and `BEGIN ATOMIC`)</span></span>  
  
-   <span data-ttu-id="a639b-112">[CREATE TABLE &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-table-transact-sql) (см.,,, `MEMORY_OPTIMIZED` `DURABILITY` `BUCKET_COUNT` `INDEX` и `HASH` ).</span><span class="sxs-lookup"><span data-stu-id="a639b-112">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) (see `MEMORY_OPTIMIZED`, `DURABILITY`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="a639b-113">[CREATE TYPE &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-type-transact-sql) (см. `MEMORY_OPTIMIZED` ,, `BUCKET_COUNT` `INDEX` и `HASH` ).</span><span class="sxs-lookup"><span data-stu-id="a639b-113">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) (see `MEMORY_OPTIMIZED`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="a639b-114">[DECLARE @local_variable &#40;&#41;TRANSACT-SQL](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (см. `NULL`  |  `NOT NULL` )</span><span class="sxs-lookup"><span data-stu-id="a639b-114">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (see `NULL` | `NOT NULL`)</span></span>  
  
 <span data-ttu-id="a639b-115">Таблицы, оптимизированные для памяти, поддерживают ограничения `PRIMARY KEY` и `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="a639b-115">Memory-optimized tables support `PRIMARY KEY` and `NOT NULL` constraints.</span></span> <span data-ttu-id="a639b-116">Дополнительные сведения о реализации неподдерживаемых ограничений см. в разделе [Миграция ограничений проверки и внешнего ключа](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="a639b-116">For information on implementing unsupported constraints, see [Migrating Check and Foreign Key Constraints](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="a639b-117">Дополнительные сведения о неподдерживаемых компонентах см. в разделе [Конструкции языка Transact-SQL, не поддерживаемые в In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="a639b-117">For information on unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a639b-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="a639b-118">In This Section</span></span>  
  
-   [<span data-ttu-id="a639b-119">Поддерживаемые типы данных</span><span class="sxs-lookup"><span data-stu-id="a639b-119">Supported Data Types</span></span>](supported-data-types-for-in-memory-oltp.md)  
  
-   [<span data-ttu-id="a639b-120">Доступ к таблицам, оптимизированным для памяти, с помощью интерпретируемых инструкций Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a639b-120">Accessing Memory-Optimized Tables Using Interpreted Transact-SQL</span></span>](accessing-memory-optimized-tables-using-interpreted-transact-sql.md)  
  
-   [<span data-ttu-id="a639b-121">Системные представления, хранимые процедуры, динамические административные представления и типы ожидания для выполняющейся в памяти OLTP</span><span class="sxs-lookup"><span data-stu-id="a639b-121">System Views, Stored Procedures, DMVs and Wait Types for In-Memory OLTP</span></span>](../../database-engine/system-views-stored-procedures-dmvs-and-wait-types-for-in-memory-oltp.md)  
  
## <a name="see-also"></a><span data-ttu-id="a639b-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="a639b-122">See Also</span></span>  
 <span data-ttu-id="a639b-123">[In-Memory OLTP (оптимизация в памяти)](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="a639b-123">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="a639b-124">[Проблемы миграции, связанные с хранимыми процедурами, скомпилированными в собственном коде](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a639b-124">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="a639b-125">[Поддерживаемые функции SQL Server](unsupported-sql-server-features-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="a639b-125">[Supported SQL Server Features](unsupported-sql-server-features-for-in-memory-oltp.md) </span></span>  
 [<span data-ttu-id="a639b-126">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="a639b-126">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
