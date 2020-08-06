---
title: Миграция в выполняющуюся в памяти OLTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 405cdac5-a0d4-47a4-9180-82876b773b82
author: rothja
ms.author: jroth
ms.openlocfilehash: ed764ce52d41d76667213b846cec51b26f634a27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750991"
---
# <a name="migrating-to-in-memory-oltp"></a><span data-ttu-id="96620-102">Миграция в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="96620-102">Migrating to In-Memory OLTP</span></span>
  <span data-ttu-id="96620-103">В данном разделе рассматривается миграция объектов базы данных для использования In-Memory OLTP.</span><span class="sxs-lookup"><span data-stu-id="96620-103">This section discusses how to migrate database objects to use In-Memory OLTP.</span></span>  
  
-   [<span data-ttu-id="96620-104">Определение, должна ли таблица или хранимая процедура быть перенесена в In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="96620-104">Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP</span></span>](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)  
  
-   [<span data-ttu-id="96620-105">Помощник по оптимизации памяти</span><span class="sxs-lookup"><span data-stu-id="96620-105">Memory Optimization Advisor</span></span>](memory-optimization-advisor.md)  
  
-   [<span data-ttu-id="96620-106">Помощник по собственной компиляции</span><span class="sxs-lookup"><span data-stu-id="96620-106">Native Compilation Advisor</span></span>](native-compilation-advisor.md)  
  
-   [<span data-ttu-id="96620-107">Конструкции языка Transact-SQL, не поддерживаемые в выполняющейся в памяти OLTP</span><span class="sxs-lookup"><span data-stu-id="96620-107">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
-   [<span data-ttu-id="96620-108">Реализация LOB Columns в таблице, оптимизированной для памяти</span><span class="sxs-lookup"><span data-stu-id="96620-108">Implementing LOB Columns in a Memory-Optimized Table</span></span>](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="96620-109">Реализация SQL_VARIANT в таблице, оптимизированной для памяти</span><span class="sxs-lookup"><span data-stu-id="96620-109">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
-   [<span data-ttu-id="96620-110">Проблемы миграции, связанные с хранимыми процедурами, скомпилированными в собственном коде</span><span class="sxs-lookup"><span data-stu-id="96620-110">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="96620-111">Перенос вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="96620-111">Migrating Computed Columns</span></span>](migrating-computed-columns.md)  
  
-   [<span data-ttu-id="96620-112">Перенос триггеров</span><span class="sxs-lookup"><span data-stu-id="96620-112">Migrating Triggers</span></span>](migrating-triggers.md)  
  
-   [<span data-ttu-id="96620-113">Межбазовые запросы</span><span class="sxs-lookup"><span data-stu-id="96620-113">Cross-Database Queries</span></span>](cross-database-queries.md)  
  
-   [<span data-ttu-id="96620-114">Миграция проверочных ограничений и ограничений внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="96620-114">Migrating Check and Foreign Key Constraints</span></span>](../../database-engine/migrating-check-and-foreign-key-constraints.md)  
  
-   [<span data-ttu-id="96620-115">Реализация IDENTITY в таблице, оптимизированной для памяти</span><span class="sxs-lookup"><span data-stu-id="96620-115">Implementing IDENTITY in a Memory-Optimized Table</span></span>](implementing-identity-in-a-memory-optimized-table.md)  
  
 <span data-ttu-id="96620-116">Дополнительные сведения о методологиях миграции см. в разделе [Выполняемая в памяти OLTP — стандартные шаблоны рабочей нагрузки и вопросы миграции](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="96620-116">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96620-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="96620-117">See Also</span></span>  
 <span data-ttu-id="96620-118">[In-Memory OLTP (оптимизация в памяти)](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="96620-118">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 [<span data-ttu-id="96620-119">Оценка требований к объему памяти для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="96620-119">Estimate Memory Requirements for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
