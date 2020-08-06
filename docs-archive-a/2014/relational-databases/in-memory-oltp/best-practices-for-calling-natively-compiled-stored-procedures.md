---
title: Рекомендации по вызову хранимых процедур, скомпилированных в собственном коде | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f39fc1c7-cfec-4a95-97f6-6b95954694bb
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d07d0e290d1fbd9b324235e64734a399bf7801d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655717"
---
# <a name="best-practices-for-calling-natively-compiled-stored-procedures"></a><span data-ttu-id="efa7e-102">Рекомендации по вызову хранимых процедур, скомпилированных в собственном коде</span><span class="sxs-lookup"><span data-stu-id="efa7e-102">Best Practices for Calling Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="efa7e-103">Скомпилированные в собственном коде хранимые процедуры:</span><span class="sxs-lookup"><span data-stu-id="efa7e-103">Natively compiled stored procedures are:</span></span>  
  
-   <span data-ttu-id="efa7e-104">обычно используются в критически важных для производительности частях приложения;</span><span class="sxs-lookup"><span data-stu-id="efa7e-104">Used typically in performance-critical parts of an application.</span></span>  
  
-   <span data-ttu-id="efa7e-105">часто выполняются;</span><span class="sxs-lookup"><span data-stu-id="efa7e-105">Frequently executed.</span></span>  
  
-   <span data-ttu-id="efa7e-106">предполагается, что отличаются очень высоким быстродействием.</span><span class="sxs-lookup"><span data-stu-id="efa7e-106">Expected to be very fast.</span></span>  
  
 <span data-ttu-id="efa7e-107">Увеличение производительности при использовании хранимой процедуры, скомпилированной в собственном коде, растет вместе с числом строк и объемом логики, которые обрабатываются в процедуре.</span><span class="sxs-lookup"><span data-stu-id="efa7e-107">The performance benefit of using a natively compiled stored procedure increases with the number of rows and the amount of logic that is processed by the procedure.</span></span> <span data-ttu-id="efa7e-108">Например, хранимая процедура, скомпилированная в собственном коде, позволяет достичь более высокой производительности, если она использует что-либо из следующего:</span><span class="sxs-lookup"><span data-stu-id="efa7e-108">For example, a natively compiled stored procedure will exhibit better performance if it uses one or more of the following:</span></span>  
  
-   <span data-ttu-id="efa7e-109">Агрегирование.</span><span class="sxs-lookup"><span data-stu-id="efa7e-109">Aggregation.</span></span>  
  
-   <span data-ttu-id="efa7e-110">Соединения вложенных циклов.</span><span class="sxs-lookup"><span data-stu-id="efa7e-110">Nested-loops joins.</span></span>  
  
-   <span data-ttu-id="efa7e-111">Операции выборки, вставки, обновления и удаления с несколькими инструкциями.</span><span class="sxs-lookup"><span data-stu-id="efa7e-111">Multi-statement select, insert, update, and delete operations.</span></span>  
  
-   <span data-ttu-id="efa7e-112">Сложные выражения.</span><span class="sxs-lookup"><span data-stu-id="efa7e-112">Complex expressions.</span></span>  
  
-   <span data-ttu-id="efa7e-113">Процедурная логика, например условные инструкции и циклы.</span><span class="sxs-lookup"><span data-stu-id="efa7e-113">Procedural logic, such as conditional statements and loops.</span></span>  
  
 <span data-ttu-id="efa7e-114">Если необходимо обработать только одну строку, применение хранимой процедуры, скомпилированной в собственном коде, может не дать прироста производительности.</span><span class="sxs-lookup"><span data-stu-id="efa7e-114">If you need to process only a single row, using a natively compiled stored procedure may not provide a performance benefit.</span></span>  
  
 <span data-ttu-id="efa7e-115">Во избежание необходимости сопоставления имен параметров и преобразования типов сервером выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="efa7e-115">To avoid the server having to map parameter names and convert types:</span></span>  
  
-   <span data-ttu-id="efa7e-116">Сопоставьте типы параметров, передаваемых процедуре, с типами в определении процедуры.</span><span class="sxs-lookup"><span data-stu-id="efa7e-116">Match the types of the parameters passed to the procedure with the types in the procedure definition.</span></span>  
  
-   <span data-ttu-id="efa7e-117">Используйте параметры с порядковыми номерами (безымянные) при вызове скомпилированных в собственном коде хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="efa7e-117">Use ordinal (nameless) parameters when calling natively compiled stored procedures.</span></span> <span data-ttu-id="efa7e-118">Для наиболее эффективного выполнения не используйте именованные параметры.</span><span class="sxs-lookup"><span data-stu-id="efa7e-118">For the most efficient execution, do not use named parameters.</span></span>  
  
 <span data-ttu-id="efa7e-119">Использование именованных параметров с хранимыми процедурами, скомпилированными в собственном коде, можно обнаружить с помощью XEvent `hekaton_slow_parameter_passing` с `reason=named_parameters`.</span><span class="sxs-lookup"><span data-stu-id="efa7e-119">Use of (inefficient) named parameters with natively compiled stored procedures can be detected through the XEvent `hekaton_slow_parameter_passing`, with `reason=named_parameters`.</span></span>  
  
 <span data-ttu-id="efa7e-120">Аналогично можно определить использование несовместимых типов через то же событие XEvent `hekaton_slow_parameter_passing` с `reason=parameter_conversion`.</span><span class="sxs-lookup"><span data-stu-id="efa7e-120">Similarly, you can detect use of mismatched types through the same XEvent `hekaton_slow_parameter_passing`, with `reason=parameter_conversion`.</span></span>  
  
 <span data-ttu-id="efa7e-121">Чтобы реализовать логику повторного выполнения при использовании таблиц с оптимизацией для памяти (во многих сценариях) и обойти ограничения некоторых функций, можно создать интерпретируемую оболочкой хранимую процедуру [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efa7e-121">Because you will need to implement retry logic when using memory-optimized tables (in many scenarios), and because you will need to work around certain feature limitations, you may want to create a wrapper interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure.</span></span> <span data-ttu-id="efa7e-122">Пример см. в разделе [рекомендации по логике повторных попыток для транзакций в таблицах, оптимизированных для памяти](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="efa7e-122">For an example, see [Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa7e-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="efa7e-123">See Also</span></span>  
 [<span data-ttu-id="efa7e-124">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="efa7e-124">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
