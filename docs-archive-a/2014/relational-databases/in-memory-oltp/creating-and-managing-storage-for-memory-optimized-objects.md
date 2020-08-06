---
title: Создание и управление хранилищем для оптимизированных для памяти объектов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 622aabe6-95c7-42cc-8768-ac2e679c5089
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 118e5e582a284023dd8e5cc71629d635e79fb989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658279"
---
# <a name="creating-and-managing-storage-for-memory-optimized-objects"></a><span data-ttu-id="ee2e9-102">Создание и управление хранилищем для оптимизированных для памяти объектов</span><span class="sxs-lookup"><span data-stu-id="ee2e9-102">Creating and Managing Storage for Memory-Optimized Objects</span></span>
  <span data-ttu-id="ee2e9-103">Механизм [!INCLUDE[hek_2](../../includes/hek-2-md.md)] интегрирован в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], что позволяет использовать оптимизированные для памяти таблицы и (традиционные) таблицы на диске в одной базе данных.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-103">The [!INCLUDE[hek_2](../../includes/hek-2-md.md)] engine is integrated into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which lets you have both memory-optimized tables and (traditional) disk-based tables in the same database.</span></span> <span data-ttu-id="ee2e9-104">Тем не менее структуры хранилища оптимизированных для памяти таблиц и таблиц на диске отличаются.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-104">However, the storage structure for memory-optimized tables is different from disk-based tables.</span></span>  
  
 <span data-ttu-id="ee2e9-105">Хранилище для таблиц на диске имеет следующие ключевые атрибуты:</span><span class="sxs-lookup"><span data-stu-id="ee2e9-105">Storage for disk-based table has following key attributes:</span></span>  
  
-   <span data-ttu-id="ee2e9-106">Оно сопоставляется с файловой группой, которая содержит один или несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-106">Mapped to a filegroup and the filegroup contains one or more files.</span></span>  
  
-   <span data-ttu-id="ee2e9-107">Каждый файл делится на экстенты по 8 страниц, а каждая страница имеет размер 8 КБ.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-107">Each file is divided into extents of 8 pages and each page is of size 8K bytes.</span></span>  
  
-   <span data-ttu-id="ee2e9-108">Экстент может совместно использоваться несколькими таблицами. Однако между выделенной страницей и таблицей или индексом устанавливается сопоставление "один к одному".</span><span class="sxs-lookup"><span data-stu-id="ee2e9-108">An extent can be shared across multiple tables, but a there is 1-to-1 mapping between an allocated page and the table or index.</span></span> <span data-ttu-id="ee2e9-109">Иными словами, страница не может содержать строки из двух или более таблиц или индексов.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-109">In other words, a page can't have rows from two or more tables or index.</span></span>  
  
-   <span data-ttu-id="ee2e9-110">Данные перемещаются в память (буферный пул) по мере необходимости. Измененные или созданные страницы асинхронно записываются на диск, создавая произвольные операции ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-110">The data is moved into memory (the buffer pool) as needed and the modified or newly created pages are asynchronously written to the disk generating mostly random IO.</span></span>  
  
 <span data-ttu-id="ee2e9-111">Хранилище оптимизированных для памяти таблиц имеет следующие ключевые атрибуты:</span><span class="sxs-lookup"><span data-stu-id="ee2e9-111">Storage for memory-optimized tables has following key attributes:</span></span>  
  
-   <span data-ttu-id="ee2e9-112">Все оптимизированные для памяти таблицы сопоставляются с оптимизированной для памяти файловой группой.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-112">All memory-optimized tables are mapped to a memory-optimized filegroup.</span></span> <span data-ttu-id="ee2e9-113">Эта файловая группа строится с использованием файловой группы FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-113">This filegroup is built using the filestream filegroup.</span></span>  
  
-   <span data-ttu-id="ee2e9-114">Страницы отсутствуют, а данные сохраняются в виде строки.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-114">There are no pages and the data is persisted as a row.</span></span>  
  
-   <span data-ttu-id="ee2e9-115">Все изменения в оптимизированных для памяти таблицах сохраняются путем добавления в активные файлы.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-115">All changes to memory-optimized tables are stored by appending to active files.</span></span> <span data-ttu-id="ee2e9-116">Операции чтения и записи в файлах выполняются последовательно.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-116">Both reading and writing to files is sequential.</span></span>  
  
-   <span data-ttu-id="ee2e9-117">Обновление реализуется как операция удаления с последующей вставкой.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-117">An update is implemented as a delete followed by an insert.</span></span> <span data-ttu-id="ee2e9-118">Удаленные строки не удаляются из хранилища немедленно.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-118">The deleted rows are not immediately removed from the storage.</span></span> <span data-ttu-id="ee2e9-119">Они удаляются фоновым процессом с именем MERGE на основе политики, как описано в статье [Устойчивость таблиц, оптимизированных для памяти](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ee2e9-119">The deleted rows are removed by a background process, called MERGE, based on a policy as described in [Durability for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
-   <span data-ttu-id="ee2e9-120">В отличие от таблиц на дисках, хранилище для оптимизированных для памяти таблиц не сжимается.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-120">Unlike disk-based tables, storage for memory-optimized tables is not compressed.</span></span> <span data-ttu-id="ee2e9-121">При переносе сжатой таблицы на диске (ROW или PAGE) в оптимизированную для памяти таблицу необходимо учитывать изменение размера.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-121">When migrating a compressed (ROW or PAGE) disk-based table to memory-optimized table, you will need to account for the change in size.</span></span>  
  
-   <span data-ttu-id="ee2e9-122">Оптимизированные для памяти таблицы могут быть постоянными или временными.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-122">A memory-optimized table can be durable or can be non-durable.</span></span> <span data-ttu-id="ee2e9-123">Необходимо настроить хранилище только для устойчивых таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-123">You only need to configure storage for durable memory-optimize tables.</span></span>  
  
 <span data-ttu-id="ee2e9-124">В этом разделе рассматриваются пары файлов контрольных точек и другие вопросы хранения оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="ee2e9-124">This section describes checkpoint file pairs and other aspects of how data in memory-optimized tables is stored.</span></span>  
  
 <span data-ttu-id="ee2e9-125">Подразделы в этом разделе:</span><span class="sxs-lookup"><span data-stu-id="ee2e9-125">Topics in this section:</span></span>  
  
-   [<span data-ttu-id="ee2e9-126">Настройка хранилища оптимизированных для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="ee2e9-126">Configuring Storage for Memory-Optimized Tables</span></span>](configuring-storage-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="ee2e9-127">Оптимизированная для памяти файловая группа</span><span class="sxs-lookup"><span data-stu-id="ee2e9-127">The Memory Optimized Filegroup</span></span>](the-memory-optimized-filegroup.md)  
  
-   [<span data-ttu-id="ee2e9-128">Устойчивость таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="ee2e9-128">Durability for Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
-   [<span data-ttu-id="ee2e9-129">Работа контрольной точки для оптимизированных для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="ee2e9-129">Checkpoint Operation for Memory-Optimized Tables</span></span>](checkpoint-operation-for-memory-optimized-tables.md)  
  
-   [<span data-ttu-id="ee2e9-130">Определение устойчивости для оптимизированных для памяти объектов</span><span class="sxs-lookup"><span data-stu-id="ee2e9-130">Defining Durability for Memory-Optimized Objects</span></span>](defining-durability-for-memory-optimized-objects.md)  
  
-   [<span data-ttu-id="ee2e9-131">Сравнение хранилища таблиц на диске с хранилищем таблиц оптимизированным для памяти</span><span class="sxs-lookup"><span data-stu-id="ee2e9-131">Comparing Disk-Based Table Storage to Memory-Optimized Table Storage</span></span>](comparing-disk-based-table-storage-to-memory-optimized-table-storage.md)  
  
-   [<span data-ttu-id="ee2e9-132">Мониторинг и устранение неполадок со слиянием для пар файлов данных и разностных файлов</span><span class="sxs-lookup"><span data-stu-id="ee2e9-132">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>](../../database-engine/monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee2e9-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="ee2e9-133">See Also</span></span>  
 [<span data-ttu-id="ee2e9-134">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="ee2e9-134">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp-in-memory-optimization.md)  
  
  
