---
title: Предварительные условия для минимального протоколирования массового импорта данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- minimal logging [SQL Server]
- logged bulk copy [SQL Server]
- logs [SQL Server], minimal logging
- minimally logged operations [SQL Server]
- bulk importing [SQL Server], minimal logging
ms.assetid: bd1dac6b-6ef8-4735-ad4e-67bb42dc4f66
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4711e25dcfcc99e14894e47166638673c61a6831
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749943"
---
# <a name="prerequisites-for-minimal-logging-in-bulk-import"></a><span data-ttu-id="a4046-102">Prerequisites for Minimal Logging in Bulk Import</span><span class="sxs-lookup"><span data-stu-id="a4046-102">Prerequisites for Minimal Logging in Bulk Import</span></span>
  <span data-ttu-id="a4046-103">В базе данных, использующей модель полного восстановления, все операции вставки строк, выполняющиеся при массовом импорте, полностью записываются в журнал транзакций.</span><span class="sxs-lookup"><span data-stu-id="a4046-103">For a database under the full recovery model, all row-insert operations that are performed by bulk import are fully logged in the transaction log.</span></span> <span data-ttu-id="a4046-104">Если используется модель полного восстановления, импорт большого количества данных может привести к быстрому заполнению журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="a4046-104">Large data imports can cause the transaction log to fill rapidly if the full recovery model is used.</span></span> <span data-ttu-id="a4046-105">При использовании простой модели восстановления или модели восстановления с неполным протоколированием минимальное протоколирование операций массового импорта, напротив, снижает вероятность того, что операция массового импорта заполнит все пространство журнала.</span><span class="sxs-lookup"><span data-stu-id="a4046-105">In contrast, under the simple recovery model or bulk-logged recovery model, minimal logging of bulk-import operations reduces the possibility that a bulk-import operation will fill the log space.</span></span> <span data-ttu-id="a4046-106">Минимальное протоколирование также более эффективно, чем полное.</span><span class="sxs-lookup"><span data-stu-id="a4046-106">Minimal logging is also more efficient than full logging.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4046-107">Модель восстановления с неполным протоколированием предназначена для временной замены модели полного восстановления на период проведения массовых операций.</span><span class="sxs-lookup"><span data-stu-id="a4046-107">The bulk-logged recovery model is designed to temporarily replace the full recovery model during large bulk operations.</span></span>  
  
## <a name="table-requirements-for-minimally-logging-bulk-import-operations"></a><span data-ttu-id="a4046-108">Требования к таблицам для минимального протоколирования операций массового импорта</span><span class="sxs-lookup"><span data-stu-id="a4046-108">Table Requirements for Minimally Logging Bulk-Import Operations</span></span>  
 <span data-ttu-id="a4046-109">Минимальное протоколирование требует, чтобы целевая таблица удовлетворяла следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="a4046-109">Minimal logging requires that the target table meets the following conditions:</span></span>  
  
-   <span data-ttu-id="a4046-110">В данный момент таблица не реплицируется.</span><span class="sxs-lookup"><span data-stu-id="a4046-110">The table is not being replicated.</span></span>  
  
-   <span data-ttu-id="a4046-111">Задана блокировка таблицы (с помощью TABLOCK).</span><span class="sxs-lookup"><span data-stu-id="a4046-111">Table locking is specified (using TABLOCK).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a4046-112">Хотя операции вставки данных при минимальном ведении журнала операций массового импорта не регистрируются в журнале транзакций, компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] по-прежнему ведет журнал выделения всех экстентов для таблицы.</span><span class="sxs-lookup"><span data-stu-id="a4046-112">Although data insertions are not logged in the transaction log during a minimally logged bulk-import operation, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] still logs extent allocations each time a new extent is allocated to the table.</span></span>  
  
-   <span data-ttu-id="a4046-113">Таблица не является оптимизированной для памяти.</span><span class="sxs-lookup"><span data-stu-id="a4046-113">Table is not a memory-optimized table.</span></span>  
  
 <span data-ttu-id="a4046-114">Можно ли использовать минимальное протоколирование, также зависит от того, индексируется ли таблица и, если это так, пуста ли она.</span><span class="sxs-lookup"><span data-stu-id="a4046-114">Whether minimal logging can occur for a table also depends on whether the table is indexed and, if so, whether the table is empty:</span></span>  
  
-   <span data-ttu-id="a4046-115">Если у таблицы нет индексов, ведется минимальный журнал страниц данных.</span><span class="sxs-lookup"><span data-stu-id="a4046-115">If the table has no indexes, data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="a4046-116">Если у таблицы нет кластеризованного индекса, но есть один или более некластеризованных индексов, всегда ведется минимальный журнал страниц данных.</span><span class="sxs-lookup"><span data-stu-id="a4046-116">If the table has no clustered index but has one or more nonclustered indexes, data pages are always minimally logged.</span></span> <span data-ttu-id="a4046-117">Однако применяемый способ ведения журнала страниц индекса зависит от того, пуста ли таблица.</span><span class="sxs-lookup"><span data-stu-id="a4046-117">How index pages are logged, however, depends on whether the table is empty:</span></span>  
  
    -   <span data-ttu-id="a4046-118">Если таблица пуста, ведется минимальный журнал страниц индекса.</span><span class="sxs-lookup"><span data-stu-id="a4046-118">If the table is empty, index pages are minimally logged.</span></span>  
  
    -   <span data-ttu-id="a4046-119">Если таблица не пуста, ведется полный журнал страниц индекса.</span><span class="sxs-lookup"><span data-stu-id="a4046-119">If table is non-empty, index pages are fully logged.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a4046-120">Если начать с пустой таблицы и выполнить массовый импорт данных несколькими пакетами, для первого пакета будет вестись минимальный журнал страниц как данных, так и индекса, но, начиная со второго пакета, минимальный журнал будет вестись только для страниц данных.</span><span class="sxs-lookup"><span data-stu-id="a4046-120">If you start with an empty table and bulk import the data in multiple batches, both index and data pages are minimally logged for the first batch, but beginning with the second batch, only data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="a4046-121">Если у таблицы есть кластеризованный индекс, и он пуст, будет вестись минимальный журнал и страниц данных, и страниц индекса.</span><span class="sxs-lookup"><span data-stu-id="a4046-121">If the table has a clustered index and is empty, both data and index pages are minimally logged.</span></span> <span data-ttu-id="a4046-122">И наоборот, если у таблицы есть непустой кластеризованный индекс, будет вестись полный журнал и страниц данных, и страниц индекса независимо от модели восстановления.</span><span class="sxs-lookup"><span data-stu-id="a4046-122">In contrast, if a table has a clustered index and is non-empty, data pages and index pages are both fully logged regardless of the recovery model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a4046-123">Если начать с пустой таблицы и выполнить массовый импорт данных несколькими пакетами, для первого пакета будет вестись минимальный журнал и страниц данных, и страниц индекса, но, начиная со второго пакета, неполный журнал будет вестись только для страниц данных.</span><span class="sxs-lookup"><span data-stu-id="a4046-123">If you start with an empty table and bulk import the data in batches, both index and data pages are minimally logged for the first batch, but from the second batch onwards, only data pages are bulk logged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4046-124">Если включена репликация транзакций, операции BULK INSERT полностью протоколируются даже в модели с неполным протоколированием.</span><span class="sxs-lookup"><span data-stu-id="a4046-124">When transactional replication is enabled, BULK INSERT operations are fully logged even under the Bulk Logged recovery model.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a4046-125">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a4046-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a4046-126">Просмотр или изменение модели восстановления базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4046-126">View or Change the Recovery Model of a Database &#40;SQL Server&#41;</span></span>](../backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="a4046-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4046-127">See Also</span></span>  
 <span data-ttu-id="a4046-128">[Модели восстановления (SQL Server)](../backup-restore/recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a4046-128">[Recovery Models &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="a4046-129">[bcp Utility](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="a4046-129">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="a4046-130">[BULK INSERT (Transact-SQL)](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4046-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="a4046-131">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4046-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="a4046-132">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4046-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="a4046-133">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4046-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="a4046-134">[Табличные указания (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="a4046-134">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 [<span data-ttu-id="a4046-135">INSERT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4046-135">INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/insert-transact-sql)  
  
  
