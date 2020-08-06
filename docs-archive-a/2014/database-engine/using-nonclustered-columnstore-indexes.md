---
title: Использование некластеризованных индексов columnstore | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
ms.assetid: 4c341fb8-7cb1-4cab-921b-e80b751d6c19
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c876eb6fdd466349ac369dcff8e292bc0839c669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732002"
---
# <a name="using-nonclustered-columnstore-indexes"></a><span data-ttu-id="353dc-102">Использование некластеризованных индексов columnstore</span><span class="sxs-lookup"><span data-stu-id="353dc-102">Using Nonclustered Columnstore Indexes</span></span>
  <span data-ttu-id="353dc-103">Описывает основные задачи при использовании некластеризованного индекса columnstore в таблице [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="353dc-103">Describes key tasks for using a nonclustered columnstore index on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="353dc-104">Общие сведения об индексах columnstore см. в разделе [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="353dc-104">For an overview of columnstore indexes, see [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span></span>

 <span data-ttu-id="353dc-105">Дополнительные сведения о кластеризованных индексах columnstore см. в разделе [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="353dc-105">For information about clustered columnstore indexes, see [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span></span>

## <a name="contents"></a><span data-ttu-id="353dc-106">Содержимое</span><span class="sxs-lookup"><span data-stu-id="353dc-106">Contents</span></span>

-   [<span data-ttu-id="353dc-107">Создание некластеризованного индекса Columnstore</span><span class="sxs-lookup"><span data-stu-id="353dc-107">Create a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#load)

-   [<span data-ttu-id="353dc-108">Изменение данных в некластеризованном индексе columnstore</span><span class="sxs-lookup"><span data-stu-id="353dc-108">Change the Data in a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#change)

##  <a name="create-a-nonclustered-columnstore-index"></a><a name="load"></a><span data-ttu-id="353dc-109">Создание некластеризованного индекса columnstore</span><span class="sxs-lookup"><span data-stu-id="353dc-109">Create a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="353dc-110">Чтобы загрузить данные в некластеризованный индекс columnstore, сначала загрузите данные в традиционную таблицу rowstore, хранящуюся в виде кучи или кластеризованного индекса, а затем используйте [инструкцию CREATE COLUMNSTORE index &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) для создания индекса columnstore.</span><span class="sxs-lookup"><span data-stu-id="353dc-110">To load data into a nonclustered columnstore index, first load data into a traditional rowstore table stored as a heap or clustered index, and then use [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) to create a columnstore index.</span></span>

 <span data-ttu-id="353dc-111">![Загрузка данных в индекс columnstore](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Загрузка данных в индекс columnstore")</span><span class="sxs-lookup"><span data-stu-id="353dc-111">![Loading data into a columnstore index](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Loading data into a columnstore index")</span></span>

##  <a name="change-the-data-in-a-nonclustered-columnstore-index"></a><a name="change"></a><span data-ttu-id="353dc-112">Изменение данных в некластеризованном индексе columnstore</span><span class="sxs-lookup"><span data-stu-id="353dc-112">Change the Data in a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="353dc-113">После создания некластеризованного индекса columnstore в таблице нельзя непосредственно изменять данные в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="353dc-113">Once you create a nonclustered columnstore index on a table, you cannot directly modify the data in that table.</span></span> <span data-ttu-id="353dc-114">Запрос с инструкциями INSERT, UPDATE, DELETE или MERGE завершится сбоем и вернет сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="353dc-114">A query with INSERT, UPDATE, DELETE, or MERGE will fail and return an error message.</span></span> <span data-ttu-id="353dc-115">Для добавления или изменения данных в таблице можно воспользоваться одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="353dc-115">To add or modify the data in the table, you can do one of the following:</span></span>

-   <span data-ttu-id="353dc-116">Отключить индекс columnstore.</span><span class="sxs-lookup"><span data-stu-id="353dc-116">Disable the columnstore index.</span></span> <span data-ttu-id="353dc-117">Затем можно обновлять данные в таблице.</span><span class="sxs-lookup"><span data-stu-id="353dc-117">You can then update the data in the table.</span></span> <span data-ttu-id="353dc-118">Если отключить индекс columnstore, то можно перестроить его после окончания обновления данных.</span><span class="sxs-lookup"><span data-stu-id="353dc-118">If you disable the columnstore index, you can rebuild the columnstore index when you finish updating the data.</span></span> <span data-ttu-id="353dc-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="353dc-119">For example:</span></span>

    ```
    ALTER INDEX mycolumnstoreindex ON mytable DISABLE;
    -- update mytable --
    ALTER INDEX mycolumnstoreindex on mytable REBUILD
    ```

-   <span data-ttu-id="353dc-120">Удалите индекс columnstore, обновите таблицу, а затем повторно создайте индекс columnstore с помощью CREATE COLUMNSTORE INDEX.</span><span class="sxs-lookup"><span data-stu-id="353dc-120">Drop the columnstore index, update the table, and then re-create the columnstore index with CREATE COLUMNSTORE INDEX.</span></span> <span data-ttu-id="353dc-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="353dc-121">For example:</span></span>

    ```
    DROP INDEX mycolumnstoreindex ON mytable
    -- update mytable --
    CREATE NONCLUSTERED COLUMNSTORE INDEX mycolumnstoreindex ON mytable;

    ```

-   <span data-ttu-id="353dc-122">Загрузка данных в промежуточную таблицу, не имеющую индекса columnstore.</span><span class="sxs-lookup"><span data-stu-id="353dc-122">Load data into a staging table that does not have a columnstore index.</span></span> <span data-ttu-id="353dc-123">Создание индекса columnstore в промежуточной таблице.</span><span class="sxs-lookup"><span data-stu-id="353dc-123">Build a columnstore index on the staging table.</span></span> <span data-ttu-id="353dc-124">Переключение промежуточной таблицы в пустую секцию главной таблицы.</span><span class="sxs-lookup"><span data-stu-id="353dc-124">Switch the staging table into an empty partition of the main table.</span></span>

-   <span data-ttu-id="353dc-125">Переключение секции из таблицы с индексом columnstore в пустую промежуточную таблицу.</span><span class="sxs-lookup"><span data-stu-id="353dc-125">Switch a partition from the table with the columnstore index into an empty staging table.</span></span> <span data-ttu-id="353dc-126">Если в промежуточной таблице имеется индекс columnstore, отключите индекс columnstore.</span><span class="sxs-lookup"><span data-stu-id="353dc-126">If there is a columnstore index on the staging table, disable the columnstore index.</span></span> <span data-ttu-id="353dc-127">Выполните все обновления.</span><span class="sxs-lookup"><span data-stu-id="353dc-127">Perform any updates.</span></span> <span data-ttu-id="353dc-128">Постройте (или перестройте) индекс columnstore.</span><span class="sxs-lookup"><span data-stu-id="353dc-128">Build (or rebuild) the columnstore index.</span></span> <span data-ttu-id="353dc-129">Переключитесь с промежуточной таблицы обратно на (теперь пустую) секцию главной таблицы.</span><span class="sxs-lookup"><span data-stu-id="353dc-129">Switch the staging table back into the (now empty) partition of the main table.</span></span>




