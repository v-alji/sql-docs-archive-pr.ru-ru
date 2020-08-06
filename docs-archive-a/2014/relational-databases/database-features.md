---
title: Функции базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 04518abb-8581-47c8-a601-ee9136c3c0eb
author: rothja
ms.author: jroth
ms.openlocfilehash: 56b9f9ba9cc6e11ea82b822ae10b31710c8617b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665380"
---
# <a name="database-features"></a><span data-ttu-id="d4ac9-102">Функции базы данных</span><span class="sxs-lookup"><span data-stu-id="d4ac9-102">Database Features</span></span>
  <span data-ttu-id="d4ac9-103">Этот раздел содержит функции и задачи, связанные с базами данных, объектами баз данных, типами данных и механизмами для работы с данными и управления ими.</span><span class="sxs-lookup"><span data-stu-id="d4ac9-103">This section contains the features and tasks associated with databases, database objects, data types, and the mechanisms used to work with or manage data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4ac9-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d4ac9-104">In This Section</span></span>  
  
|||
|--|--|
|[<span data-ttu-id="d4ac9-105">Базы данных</span><span class="sxs-lookup"><span data-stu-id="d4ac9-105">Databases</span></span>](databases/databases.md)|[<span data-ttu-id="d4ac9-106">Резервное копирование и восстановление баз данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4ac9-106">Back Up and Restore of SQL Server Databases</span></span>](backup-restore/back-up-and-restore-of-sql-server-databases.md)|  
|[<span data-ttu-id="d4ac9-107">Таблицы</span><span class="sxs-lookup"><span data-stu-id="d4ac9-107">Tables</span></span>](tables/tables.md)|[<span data-ttu-id="d4ac9-108">Порядковые номера</span><span class="sxs-lookup"><span data-stu-id="d4ac9-108">Sequence Numbers</span></span>](sequence-numbers/sequence-numbers.md)|[<span data-ttu-id="d4ac9-109">Массовый импорт и экспорт данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-109">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](import-export/bulk-import-and-export-of-data-sql-server.md)|  
|[<span data-ttu-id="d4ac9-110">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-110">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp/in-memory-oltp-in-memory-optimization.md)|[<span data-ttu-id="d4ac9-111">Триггеры DDL</span><span class="sxs-lookup"><span data-stu-id="d4ac9-111">DDL Triggers</span></span>](triggers/ddl-triggers.md)|[<span data-ttu-id="d4ac9-112">Сжатие данных</span><span class="sxs-lookup"><span data-stu-id="d4ac9-112">Data Compression</span></span>](data-compression/data-compression.md)|  
|[<span data-ttu-id="d4ac9-113">Индексы</span><span class="sxs-lookup"><span data-stu-id="d4ac9-113">Indexes</span></span>](indexes/indexes.md)|[<span data-ttu-id="d4ac9-114">Триггеры DML</span><span class="sxs-lookup"><span data-stu-id="d4ac9-114">DML Triggers</span></span>](triggers/dml-triggers.md)|[<span data-ttu-id="d4ac9-115">Объекты OLE-автоматизации в Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d4ac9-115">OLE Automation Objects in Transact-SQL</span></span>](stored-procedures/ole-automation-objects-in-transact-sql.md)|  
|[<span data-ttu-id="d4ac9-116">Partitioned Tables and Indexes</span><span class="sxs-lookup"><span data-stu-id="d4ac9-116">Partitioned Tables and Indexes</span></span>](partitions/partitioned-tables-and-indexes.md)|[<span data-ttu-id="d4ac9-117">Синонимы (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-117">Synonyms &#40;Database Engine&#41;</span></span>](synonyms/synonyms-database-engine.md)|[<span data-ttu-id="d4ac9-118">Уведомления о событиях</span><span class="sxs-lookup"><span data-stu-id="d4ac9-118">Event Notifications</span></span>](service-broker/event-notifications.md)|  
|[<span data-ttu-id="d4ac9-119">Представления</span><span class="sxs-lookup"><span data-stu-id="d4ac9-119">Views</span></span>](views/views.md)|[<span data-ttu-id="d4ac9-120">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-120">XML Data &#40;SQL Server&#41;</span></span>](xml/xml-data-sql-server.md)|[<span data-ttu-id="d4ac9-121">Наблюдение и настройка производительности</span><span class="sxs-lookup"><span data-stu-id="d4ac9-121">Monitor and Tune for Performance</span></span>](performance/monitor-and-tune-for-performance.md)|  
|[<span data-ttu-id="d4ac9-122">Хранимые процедуры (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-122">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures/stored-procedures-database-engine.md)|[<span data-ttu-id="d4ac9-123">Пространственные данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial/spatial-data-sql-server.md)||  
|[<span data-ttu-id="d4ac9-124">Поиск SQL Server &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ac9-124">Search &#40;SQL Server&#41;</span></span>](../database-engine/search-sql-server.md)|[<span data-ttu-id="d4ac9-125">Данные большого двоичного объекта (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-125">Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;</span></span>](blob/binary-large-object-blob-data-sql-server.md)||  
|[<span data-ttu-id="d4ac9-126">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="d4ac9-126">User-Defined Functions</span></span>](user-defined-functions/user-defined-functions.md)|[<span data-ttu-id="d4ac9-127">Приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="d4ac9-127">Data-tier Applications</span></span>](data-tier-applications/data-tier-applications.md)||  
|[<span data-ttu-id="d4ac9-128">Статистика</span><span class="sxs-lookup"><span data-stu-id="d4ac9-128">Statistics</span></span>](statistics/statistics.md)|[<span data-ttu-id="d4ac9-129">Журнал транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-129">The Transaction Log &#40;SQL Server&#41;</span></span>](logs/the-transaction-log-sql-server.md)||  
|[<span data-ttu-id="d4ac9-130">Руководства планов</span><span class="sxs-lookup"><span data-stu-id="d4ac9-130">Plan Guides</span></span>](performance/plan-guides.md)|[<span data-ttu-id="d4ac9-131">Контрольные точки базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d4ac9-131">Database Checkpoints &#40;SQL Server&#41;</span></span>](logs/database-checkpoints-sql-server.md)||  
  
  
