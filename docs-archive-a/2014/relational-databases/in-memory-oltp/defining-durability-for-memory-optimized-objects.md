---
title: Определение устойчивости для оптимизированных для памяти объектов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0fe85fbf-8e8d-4983-96fd-d04b3c7d6d65
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 325f50a74ea75270dd62fc3564200c59255dc6cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657091"
---
# <a name="defining-durability-for-memory-optimized-objects"></a><span data-ttu-id="30394-102">Определение устойчивости для оптимизированных для памяти объектов</span><span class="sxs-lookup"><span data-stu-id="30394-102">Defining Durability for Memory-Optimized Objects</span></span>
  <span data-ttu-id="30394-103">OLTP в памяти гарантирует полную атомарность, согласованность, изолированность и устойчивость (ACID).</span><span class="sxs-lookup"><span data-stu-id="30394-103">In-Memory OLTP guarantees full atomicity, consistency, isolation, and full durability (ACID) properties.</span></span> <span data-ttu-id="30394-104">Устойчивость в контексте [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и оптимизированных для памяти таблиц предоставляет следующие гарантии.</span><span class="sxs-lookup"><span data-stu-id="30394-104">Durability in the context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and memory-optimized tables provides following guarantees:</span></span>  
  
 <span data-ttu-id="30394-105">Надежность транзакций</span><span class="sxs-lookup"><span data-stu-id="30394-105">Transactional Durability</span></span>  
 <span data-ttu-id="30394-106">После фиксации полностью устойчивой транзакции, которая внесла изменения (DDL или DML) в оптимизированную для памяти таблицу, изменения в устойчивой таблице, оптимизированной для памяти, становятся постоянными.</span><span class="sxs-lookup"><span data-stu-id="30394-106">When you commit a fully durable transaction that made (DDL or DML) changes to a memory-optimized table, the changes made to a durable memory-optimized table are permanent.</span></span>  
  
 <span data-ttu-id="30394-107">При фиксации отложенной устойчивой транзакции в оптимизированной для памяти таблице в памяти транзакция становится устойчивой только после того, как журнал транзакций в памяти записывается на диск.</span><span class="sxs-lookup"><span data-stu-id="30394-107">When you commit a delayed durable transaction to a memory-optimized table, the transaction becomes durable only after the in-memory transaction log is saved to disk.</span></span>  
  
 <span data-ttu-id="30394-108">Устойчивость при перезапуске</span><span class="sxs-lookup"><span data-stu-id="30394-108">Restart Durability</span></span>  
 <span data-ttu-id="30394-109">При перезапуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] после сбоя или запланированного завершения работы для устойчивых, оптимизированных для памяти таблиц повторно создаются экземпляры, чтобы вернуть их в состояние перед завершением работы или сбоем.</span><span class="sxs-lookup"><span data-stu-id="30394-109">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restarts after a crash or planned shutdown, the memory-optimized durable tables are reinstantiated to restore them to the state before the shutdown or crash.</span></span>  
  
 <span data-ttu-id="30394-110">Устойчивость при сбое носителя</span><span class="sxs-lookup"><span data-stu-id="30394-110">Media Failure Durability</span></span>  
 <span data-ttu-id="30394-111">Если поврежденный или недоступный диск содержит одну или несколько копий устойчивых, оптимизированных для памяти объектов, то компонент резервного копирования и восстановления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] восстанавливает оптимизированные для памяти таблицы на новом носителе.</span><span class="sxs-lookup"><span data-stu-id="30394-111">If a failed or corrupt disk contains one or more persisted copies of durable memory-optimized objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore feature restores memory-optimized tables on the new media.</span></span>  
  
 <span data-ttu-id="30394-112">Существует два параметра устойчивости для оптимизированных для памяти таблиц:</span><span class="sxs-lookup"><span data-stu-id="30394-112">There are two durability options for memory-optimized tables:</span></span>  
  
 <span data-ttu-id="30394-113">SCHEMA_ONLY (недолговечная таблица)</span><span class="sxs-lookup"><span data-stu-id="30394-113">SCHEMA_ONLY (non-durable table)</span></span>  
 <span data-ttu-id="30394-114">Этот параметр обеспечивает устойчивость схемы таблицы, в том числе индексов.</span><span class="sxs-lookup"><span data-stu-id="30394-114">This option ensures durability of the table schema, including indexes.</span></span> <span data-ttu-id="30394-115">При перезапуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] недолговечная таблица создается заново, но запускается без данных.</span><span class="sxs-lookup"><span data-stu-id="30394-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted, the non-durable table is recreated, but starts with no data.</span></span> <span data-ttu-id="30394-116">(В отличие от таблицы в базе данных tempdb, где и таблица, и ее данные теряются после перезапуска.) Типичный сценарий для создания недолговечной таблицы — хранение временных данных, например промежуточной таблицы для процесса ETL.</span><span class="sxs-lookup"><span data-stu-id="30394-116">(This is unlike a table in tempdb, where both the table and its data are lost upon restart.) A typical scenario for creating a non-durable table is to store transient data, such as a staging table for an ETL process.</span></span> <span data-ttu-id="30394-117">Устойчивость SCHEMA_ONLY предотвращает ведение журнала транзакций и создание контрольной точки, что может существенно уменьшить объем операций ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="30394-117">A SCHEMA_ONLY durability avoids both transaction logging and checkpoint, which can significantly reduce I/O operations.</span></span>  
  
 <span data-ttu-id="30394-118">SCHEMA_AND_DATA (долговечная таблица)</span><span class="sxs-lookup"><span data-stu-id="30394-118">SCHEMA_AND_DATA (durable table)</span></span>  
 <span data-ttu-id="30394-119">Этот параметр обеспечивает устойчивость как схем, так и данных.</span><span class="sxs-lookup"><span data-stu-id="30394-119">This option provides durability of both schema and data.</span></span> <span data-ttu-id="30394-120">Уровень устойчивости данных зависит от того, выбрана ли фиксация транзакции как полностью устойчивая или отложенно устойчивая.</span><span class="sxs-lookup"><span data-stu-id="30394-120">The level of data durability depends on whether you commit a transaction as fully durable or with delayed durability.</span></span> <span data-ttu-id="30394-121">Полностью устойчивые транзакции дают гарантию устойчивости данных и схемы аналогично таблице на диске.</span><span class="sxs-lookup"><span data-stu-id="30394-121">Fully durable transactions provide the same durability guarantee for data and schema, similar to a disk-based table.</span></span> <span data-ttu-id="30394-122">Отложенная устойчивость улучшает производительность, но может привести к потере данных в случае сбоя или отработки отказа сервера.</span><span class="sxs-lookup"><span data-stu-id="30394-122">Delayed durability will improve performance but can potentially result in data loss in case of a server crash or fail over.</span></span> <span data-ttu-id="30394-123">(Дополнительные сведения об отложенной устойчивости см. в разделе [Управление устойчивостью транзакций](../logs/control-transaction-durability.md).)</span><span class="sxs-lookup"><span data-stu-id="30394-123">(For more information about delayed durability, see [Control Transaction Durability](../logs/control-transaction-durability.md).)</span></span>  
  
 <span data-ttu-id="30394-124">Схема оптимизированной для памяти таблицы сохраняется, как и для таблиц на диске, в первичной файловой группе базы данных.</span><span class="sxs-lookup"><span data-stu-id="30394-124">The schema of the memory-optimized table is persisted, similar to disk-based tables, in the primary file group of a database.</span></span>  
  
 <span data-ttu-id="30394-125">Данные в устойчивой, оптимизированной для памяти таблице сохраняются на диск в парах из файла данных и разностного файла.</span><span class="sxs-lookup"><span data-stu-id="30394-125">Data in durable memory-optimized tables is saved in data and delta file pairs.</span></span>  
  
 <span data-ttu-id="30394-126">Индексы, определенные в оптимизированных для памяти таблицах, сохраняются только в метаданных, но не в хранилище.</span><span class="sxs-lookup"><span data-stu-id="30394-126">The indexes defined in memory-optimized tables persist only in metadata, not in storage.</span></span> <span data-ttu-id="30394-127">Структуры индексов создаются при загрузке оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="30394-127">Index structures are generated as part of loading memory-optimized tables.</span></span>  
  
 <span data-ttu-id="30394-128">Строки удаляются явным образом с помощью инструкции DELETE или неявно с помощью инструкции UPDATE.</span><span class="sxs-lookup"><span data-stu-id="30394-128">Rows are deleted either explicitly by a DELETE statement or indirectly by an UPDATE statement.</span></span> <span data-ttu-id="30394-129">Операция UPDATE выполняется как удаление с последующей вставкой.</span><span class="sxs-lookup"><span data-stu-id="30394-129">An UPDATE operation is executed as a delete followed by an insert.</span></span> <span data-ttu-id="30394-130">При удалении строки в файл данных не вносятся никакие изменения, а новая строка, определяющая удаленную строку, добавляется в соответствующий разностный файл.</span><span class="sxs-lookup"><span data-stu-id="30394-130">When a row is deleted, no change is made to a data file but a new row, identifying the deleted row, is appended to the corresponding delta file.</span></span>  
  
 <span data-ttu-id="30394-131">Во время операций восстановления подсистема OLTP в памяти считывает файлы данных и разностные файлы для загрузки в физическую память.</span><span class="sxs-lookup"><span data-stu-id="30394-131">During recovery or restore operations, the In-Memory OLTP engine reads data and delta files for loading into physical memory.</span></span> <span data-ttu-id="30394-132">Время загрузки определяется следующими факторами:</span><span class="sxs-lookup"><span data-stu-id="30394-132">The load time is determined by:</span></span>  
  
-   <span data-ttu-id="30394-133">объем данных для загрузки;</span><span class="sxs-lookup"><span data-stu-id="30394-133">The amount of data to load.</span></span>  
  
-   <span data-ttu-id="30394-134">пропускная способность операций последовательного ввода-вывода;</span><span class="sxs-lookup"><span data-stu-id="30394-134">Sequential I/O bandwidth.</span></span>  
  
-   <span data-ttu-id="30394-135">степень параллелизма, определенная числом контейнеров файла и процессорных ядер.</span><span class="sxs-lookup"><span data-stu-id="30394-135">Degree of parallelism, determined by number of file containers and processor cores.</span></span>  
  
-   <span data-ttu-id="30394-136">Количество записей журнала в активной части журнала, которые нужно перезаписать.</span><span class="sxs-lookup"><span data-stu-id="30394-136">The amount of log records in the active portion of the log that need to be redone.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30394-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="30394-137">See Also</span></span>  
 [<span data-ttu-id="30394-138">Создание и управление хранилищем для оптимизированных для памяти объектов</span><span class="sxs-lookup"><span data-stu-id="30394-138">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
