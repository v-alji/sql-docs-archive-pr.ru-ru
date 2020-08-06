---
title: Оптимизированные для памяти таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 14dddf81-b502-49dc-a6b6-d18b1ae32d2b
author: rothja
ms.author: jroth
ms.openlocfilehash: 73430505e55230daf31c492d882eadeb6d35d29f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749896"
---
# <a name="memory-optimized-tables"></a><span data-ttu-id="1bff5-102">Таблицы, оптимизированные для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-102">Memory-Optimized Tables</span></span>
  <span data-ttu-id="1bff5-103">Операции OLTP в памяти[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] повышают производительность OLTP-приложений благодаря эффективному, оптимизированному для памяти доступу к данным, собственной компиляции бизнес-логики и алгоритмам без кратковременной блокировки.</span><span class="sxs-lookup"><span data-stu-id="1bff5-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] In-Memory OLTP helps improve performance of OLTP applications through efficient, memory-optimized data access, native compilation of business logic, and lock- and latch free algorithms.</span></span> <span data-ttu-id="1bff5-104">Функциональность OLTP-операций в памяти обеспечивается оптимизированными для памяти таблицами и табличными типами, а также собственной компиляцией хранимых процедур [!INCLUDE[tsql](../../includes/tsql-md.md)] для эффективного доступа к этим таблицам.</span><span class="sxs-lookup"><span data-stu-id="1bff5-104">The In-Memory OLTP feature includes memory-optimized tables and table types, as well as native compilation of [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures for efficient access to these tables.</span></span>  
  
 <span data-ttu-id="1bff5-105">Дополнительные сведения об оптимизированных для памяти таблицах см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="1bff5-105">For more information about memory-optimized tables, see:</span></span>  
  
-   [<span data-ttu-id="1bff5-106">Введение в таблицы, оптимизированные для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-106">Introduction to Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
     <span data-ttu-id="1bff5-107">Сведения о том, что такое оптимизированные для памяти таблицы, и информация об устойчивости данных, получении доступа к данным в оптимизированных для памяти таблицах, производительности и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="1bff5-107">Details what memory-optimized tables are and provides information about data durability, accessing data in memory-optimized tables, and performance and scalability.</span></span>  
  
-   [<span data-ttu-id="1bff5-108">Собственная компиляция таблиц и хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="1bff5-108">Native Compilation of Tables and Stored Procedures</span></span>](../in-memory-oltp/natively-compiled-stored-procedures.md)  
  
     <span data-ttu-id="1bff5-109">Компиляция оптимизированных для памяти таблиц и хранимых процедур, скомпилированных в собственном коде, в DLL-файлы, а также связанные рекомендации по безопасности.</span><span class="sxs-lookup"><span data-stu-id="1bff5-109">Details how memory-optimized tables and natively compiled stored procedures are compiled into DLLs, and provides related security considerations.</span></span>  
  
-   [<span data-ttu-id="1bff5-110">Изменение таблиц с оптимизацией для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-110">Altering Memory-Optimized Tables</span></span>](altering-memory-optimized-tables.md)  
  
     <span data-ttu-id="1bff5-111">Руководства по обновлению оптимизированных для памяти таблиц (включая изменение столбцов таблиц, индексов и объектов bucket_count).</span><span class="sxs-lookup"><span data-stu-id="1bff5-111">Guidelines for updating memory-optimized tables (including changing table columns, indexes, and bucket_count).</span></span>  
  
-   [<span data-ttu-id="1bff5-112">Основные сведения о транзакциях с таблицами, оптимизированными для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-112">Understanding Transactions on Memory-Optimized Tables</span></span>](../../database-engine/understanding-transactions-on-memory-optimized-tables.md)  
  
     <span data-ttu-id="1bff5-113">В этом разделе представлены несколько подразделов, связанных с выполнением транзакций в оптимизированных для памяти таблицах, включая уровни изоляции транзакций и транзакции между контейнерами.</span><span class="sxs-lookup"><span data-stu-id="1bff5-113">This section provides several topics related to performing transactions on memory-optimized tables including transaction isolation levels, and cross-container transactions.</span></span>  
  
-   [<span data-ttu-id="1bff5-114">Модель приложения для секционирования таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-114">Application Pattern for Partitioning Memory-Optimized Tables</span></span>](application-pattern-for-partitioning-memory-optimized-tables.md)  
  
     <span data-ttu-id="1bff5-115">Подробный пример кода, который показывает, как эмулировать секционированные таблицы, оптимизированные для памяти.</span><span class="sxs-lookup"><span data-stu-id="1bff5-115">Detailed code sample that shows how to emulate partitioned tables when using memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="1bff5-116">Статистика для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-116">Statistics for Memory-Optimized Tables</span></span>](statistics-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="1bff5-117">Компиляция статистики в оптимизированных для памяти таблицах и сохранение и выполняемое вручную обновление статистики таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="1bff5-117">Details how statistics are compiled for memory-optimized tables and how to maintain and manually update statistics for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="1bff5-118">Параметры сортировки и кодовые страницы</span><span class="sxs-lookup"><span data-stu-id="1bff5-118">Collations and Code Pages</span></span>](../../database-engine/collations-and-code-pages.md)  
  
     <span data-ttu-id="1bff5-119">Ограничения в поддерживаемых параметрах сортировки и кодировках для таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="1bff5-119">Details the restrictions on supported collations and code pages for memory-optimized tables.</span></span>  
  
-   [<span data-ttu-id="1bff5-120">Размер строк и таблицы для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-120">Table and Row Size in Memory-Optimized Tables</span></span>](table-and-row-size-in-memory-optimized-tables.md)  
  
     <span data-ttu-id="1bff5-121">Лимит строк в 8 060 байт таблиц, оптимизированных для памяти, и пример расчета таблицы и размеров строк.</span><span class="sxs-lookup"><span data-stu-id="1bff5-121">Details the 8060 byte limit on memory-optimized table rows, and provides an example for calculating table and row sizes.</span></span>  
  
-   [<span data-ttu-id="1bff5-122">Руководство по обработке запросов для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="1bff5-122">A Guide to Query Processing for Memory-Optimized Tables</span></span>](a-guide-to-query-processing-for-memory-optimized-tables.md)  
  
     <span data-ttu-id="1bff5-123">Обзор обработки запросов для таблиц, оптимизированных для памяти, и хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="1bff5-123">Provides an overview of query processing for both memory-optimized tables, and natively compiled stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bff5-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bff5-124">See Also</span></span>  
 [<span data-ttu-id="1bff5-125">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="1bff5-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
