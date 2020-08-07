---
title: Основные сведения о транзакциях в таблицах, оптимизированных для памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0671bba8b7a0bda27ea27cf059cb9e3b1bb87b2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732890"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a><span data-ttu-id="862b3-102">Основные сведения о транзакциях с таблицами, оптимизированными для памяти</span><span class="sxs-lookup"><span data-stu-id="862b3-102">Understanding Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="862b3-103">Транзакции обращаются к оптимизированным для памяти таблицам с использованием управления оптимистичным параллелизмом с различными версиями.</span><span class="sxs-lookup"><span data-stu-id="862b3-103">Transactions access memory-optimized tables using a form of optimistic, multi-version concurrency control.</span></span> <span data-ttu-id="862b3-104">Это означает, что существуют разные версии данных.</span><span class="sxs-lookup"><span data-stu-id="862b3-104">This means that there are different versions of the data.</span></span> <span data-ttu-id="862b3-105">Каждая транзакция работает с собственной транзакционно согласованной версией базы данных независимо от других одновременно выполняемых транзакций.</span><span class="sxs-lookup"><span data-stu-id="862b3-105">Each transaction operates on its own transactionally consistent version of the database, independent from other concurrently running transactions.</span></span> <span data-ttu-id="862b3-106">Кроме того, транзакции работают с оптимистическим допущением об отсутствии конфликтов с другими параллельными транзакциями.</span><span class="sxs-lookup"><span data-stu-id="862b3-106">In addition, transactions operate under the optimistic assumption that there will be no conflicts with other, concurrent, transactions.</span></span> <span data-ttu-id="862b3-107">В результате исключается необходимость в использовании блокировок, но требуется, чтобы система обнаруживала конфликты и завершала одну из конфликтующих транзакций.</span><span class="sxs-lookup"><span data-stu-id="862b3-107">This avoids the need to use locks, but does require the system to detect conflicts and terminate one of the conflicting transactions.</span></span> <span data-ttu-id="862b3-108">Конфликты могут возникать только для транзакций «запись-запись» и транзакций «чтение-запись».</span><span class="sxs-lookup"><span data-stu-id="862b3-108">Conflicts can occur only for write-write transactions and for read-write transactions.</span></span> <span data-ttu-id="862b3-109">При наличии конфликта между двумя операциями записи одна транзакция записи будет завершена принудительно.</span><span class="sxs-lookup"><span data-stu-id="862b3-109">If there is a write-write conflict, one write transaction is terminated.</span></span>  
  
 <span data-ttu-id="862b3-110">Существует сходство между управлением параллелизмом оптимизированных для памяти таблиц и управлением параллелизмом для дисковых таблиц READ_COMMITTED_SNAPSHOT и уровней изоляции транзакции SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="862b3-110">There are similarities between the concurrency control for memory-optimized tables and the concurrency control for disk-based tables for the READ_COMMITTED_SNAPSHOT and SNAPSHOT transaction isolation levels.</span></span> <span data-ttu-id="862b3-111">(Дополнительные сведения о дисковых таблицах см. [в разделе уровни изоляции, основанные на управлении версиями строк, в ядро СУБД](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span><span class="sxs-lookup"><span data-stu-id="862b3-111">(For more information about disk-based tables, see [Row Versioning-based Isolation Levels in the Database Engine](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx).)</span></span>  
  
## <a name="topics-in-this-section"></a><span data-ttu-id="862b3-112">Подразделы в этом разделе</span><span class="sxs-lookup"><span data-stu-id="862b3-112">Topics in This Section</span></span>  
 <span data-ttu-id="862b3-113">Этот раздел о транзакциях в таблицах с оптимизацией для памяти включает следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="862b3-113">This section on transactions in memory-optimized tables includes the following topics:</span></span>  
  
-   [<span data-ttu-id="862b3-114">Рекомендации для уровней изоляции транзакций с таблицами, оптимизированными для памяти</span><span class="sxs-lookup"><span data-stu-id="862b3-114">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [<span data-ttu-id="862b3-115">Рекомендации для логики повторного выполнения транзакций для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="862b3-115">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="862b3-116">Транзакции в таблицах, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="862b3-116">Transactions in Memory-Optimized Tables</span></span>](transactions-in-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="862b3-117">Уровни изоляции транзакций</span><span class="sxs-lookup"><span data-stu-id="862b3-117">Transaction Isolation Levels</span></span>](transaction-isolation-levels.md)  
  
-   [<span data-ttu-id="862b3-118">Транзакции между контейнерами</span><span class="sxs-lookup"><span data-stu-id="862b3-118">Cross-Container Transactions</span></span>](cross-container-transactions.md)  
  
 <span data-ttu-id="862b3-119">Дополнительные сведения см. в разделе [Управление устойчивостью транзакций](../relational-databases/logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="862b3-119">For more information, see [Control Transaction Durability](../relational-databases/logs/control-transaction-durability.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="862b3-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="862b3-120">See Also</span></span>  
 [<span data-ttu-id="862b3-121">Таблицы, оптимизированные для памяти</span><span class="sxs-lookup"><span data-stu-id="862b3-121">Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
