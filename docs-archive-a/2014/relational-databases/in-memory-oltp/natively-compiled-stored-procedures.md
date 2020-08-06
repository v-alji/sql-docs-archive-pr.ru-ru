---
title: Хранимые процедуры, скомпилированные в собственном коде | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- natively compiled stored procedures
ms.assetid: d5ed432c-10c5-4e4f-883c-ef4d1fa32366
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b8fb7a379c0c08ca357baa1042ebcf51c512c9ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738378"
---
# <a name="natively-compiled-stored-procedures"></a><span data-ttu-id="9a257-102">скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="9a257-102">Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="9a257-103">Скомпилированные в собственном коде хранимые процедуры — это хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] , скомпилированные в машинный код, который обращается к таблицам с оптимизацией для памяти.</span><span class="sxs-lookup"><span data-stu-id="9a257-103">Natively compiled stored procedures are [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures compiled to native code that access memory-optimized tables.</span></span> <span data-ttu-id="9a257-104">Скомпилированные в собственном коде хранимые процедуры позволяют эффективно выполнять запросы и бизнес-логику в хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="9a257-104">Natively compiled stored procedures allow for efficient execution of queries and business logic in the stored procedure.</span></span> <span data-ttu-id="9a257-105">Дополнительные сведения о процессе компиляции в собственный код см. в разделе [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9a257-105">For more details about the native compilation process, see [Native Compilation of Tables and Stored Procedures](native-compilation-of-tables-and-stored-procedures.md).</span></span> <span data-ttu-id="9a257-106">Дополнительные сведения о миграции дисковых хранимых процедур в скомпилированные в собственном коде хранимые процедуры см. в разделе [Проблемы миграции, связанные с хранимыми процедурами, которые скомпилированы в собственном коде](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9a257-106">For more information about migrating disk-based stored procedures to natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a257-107">Одним из различий между интерпретируемыми (дисковыми) хранимыми процедурами и хранимыми процедурами, скомпилированными в собственном коде, является то, что интерпретируемые хранимые процедуры компилируются при первом выполнении, а хранимые процедуры, скомпилированные в собственном коде, компилируются при их создании.</span><span class="sxs-lookup"><span data-stu-id="9a257-107">One difference between interpreted (disk-based) stored procedures and natively compiled stored procedures is that an interpreted stored procedure is compiled at first execution whereas a natively compiled stored procedure is compiled when it is created.</span></span> <span data-ttu-id="9a257-108">При работе со скомпилированными хранимыми процедурами многие ошибочные ситуации (арифметическое переполнение, преобразование типов и в некоторых случаях деления на нуль) могут быть обнаружены во время создания, что приведет к неуспешному завершению операции создания компилируемой хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="9a257-108">With natively compiled stored procedures, many error conditions (arithmetic overflow, type conversion, and some divide-by-zero conditions) can be detected at create time and will cause creation of the natively compiled stored procedure to fail.</span></span> <span data-ttu-id="9a257-109">При работе с интерпретируемыми хранимыми процедурами эти ошибочные ситуации обычно не приводят к появлению ошибок при создании хранимой процедуры, но все выполнения такой процедуры завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9a257-109">With interpreted stored procedures, these error conditions will typically not cause a failure when the stored procedure is created, but all executions will fail.</span></span>  
  
 <span data-ttu-id="9a257-110">Подразделы в этом разделе:</span><span class="sxs-lookup"><span data-stu-id="9a257-110">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="9a257-111">Создание хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9a257-111">Creating Natively Compiled Stored Procedures</span></span>](creating-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="9a257-112">Блоки Atomic</span><span class="sxs-lookup"><span data-stu-id="9a257-112">Atomic Blocks</span></span>](atomic-blocks-in-native-procedures.md)  
  
-   [<span data-ttu-id="9a257-113">Поддерживаемые конструкции для хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9a257-113">Supported Constructs in Natively Compiled Stored Procedures</span></span>](supported-features-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="9a257-114">Использование блоков try..catch в хранимых процедурах, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9a257-114">Using Try..Catch in Natively Compiled Stored Procedures</span></span>](../../database-engine/using-try-catch-in-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="9a257-115">Поддерживаемые конструкции для хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9a257-115">Supported Constructs on Natively Compiled Stored Procedures</span></span>](supported-ddl-for-natively-compiled-t-sql-modules.md)  
  
-   [<span data-ttu-id="9a257-116">Скомпилированные в собственном коде хранимые процедуры и параметры SET выполнения</span><span class="sxs-lookup"><span data-stu-id="9a257-116">Natively Compiled Stored Procedures and Execution Set Options</span></span>](natively-compiled-stored-procedures-and-execution-set-options.md)  
  
-   [<span data-ttu-id="9a257-117">Рекомендации по вызову хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="9a257-117">Best Practices for Calling Natively Compiled Stored Procedures</span></span>](best-practices-for-calling-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="9a257-118">Отслеживание производительности скомпилированных в собственном коде хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="9a257-118">Monitoring Performance of Natively Compiled Stored Procedures</span></span>](monitoring-performance-of-natively-compiled-stored-procedures.md)  
  
-   [<span data-ttu-id="9a257-119">Вызов хранимых процедур, скомпилированных в собственном коде, из приложений для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="9a257-119">Calling Natively Compiled Stored Procedures from Data Access Applications</span></span>](calling-natively-compiled-stored-procedures-from-data-access-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a257-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a257-120">See Also</span></span>  
 [<span data-ttu-id="9a257-121">Таблицы, оптимизированные для памяти</span><span class="sxs-lookup"><span data-stu-id="9a257-121">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
