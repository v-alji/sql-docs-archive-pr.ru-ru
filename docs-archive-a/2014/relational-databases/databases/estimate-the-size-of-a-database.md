---
title: Оценка размера базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], database size
- calculating database size
- increasing database size
- database size [SQL Server], estimating
- predicting database size
- size [SQL Server], databases
- estimating database size
- designing databases [SQL Server], estimating size
ms.assetid: 5b240161-eba4-44b0-946c-61a8fc00fc8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3a390c4ade2c2dc08f67d2d1461955516e866c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658812"
---
# <a name="estimate-the-size-of-a-database"></a><span data-ttu-id="43afb-102">Оценка размера базы данных</span><span class="sxs-lookup"><span data-stu-id="43afb-102">Estimate the Size of a Database</span></span>
  <span data-ttu-id="43afb-103">При проектировании базы данных иногда требуется оценить, каким будет размер базы данных после заполнения ее данными.</span><span class="sxs-lookup"><span data-stu-id="43afb-103">When you design a database, you may have to estimate how large the database will be when filled with data.</span></span> <span data-ttu-id="43afb-104">Оценка размера базы данных помогает определить конфигурацию аппаратного обеспечения, необходимую для достижения следующих целей:</span><span class="sxs-lookup"><span data-stu-id="43afb-104">Estimating the size of the database can help you determine the hardware configuration you will require to do the following:</span></span>  
  
-   <span data-ttu-id="43afb-105">Получения производительности, необходимой для работы приложений.</span><span class="sxs-lookup"><span data-stu-id="43afb-105">Achieve the performance required by your applications.</span></span>  
  
-   <span data-ttu-id="43afb-106">Обеспечения соответствующего физического объема места на диске, необходимого для хранения данных и индексов.</span><span class="sxs-lookup"><span data-stu-id="43afb-106">Guarantee the appropriate physical amount of disk space required to store the data and indexes.</span></span>  
  
 <span data-ttu-id="43afb-107">Оценка размера базы данных помогает определить, требуется ли доработка проекта базы данных.</span><span class="sxs-lookup"><span data-stu-id="43afb-107">Estimating the size of a database can also help you determine whether the database design needs refining.</span></span> <span data-ttu-id="43afb-108">Например, может оказаться, что предполагаемый размер базы данных слишком велик для предприятия, а потому требуется ее нормализация.</span><span class="sxs-lookup"><span data-stu-id="43afb-108">For example, you may determine that the estimated size of the database is too large to implement in your organization and that more normalization is required.</span></span> <span data-ttu-id="43afb-109">Напротив, оценочный размер может оказаться меньше, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="43afb-109">Conversely, the estimated size may be smaller than expected.</span></span> <span data-ttu-id="43afb-110">Это позволит денормализовать базу данных для повышения производительности запросов.</span><span class="sxs-lookup"><span data-stu-id="43afb-110">This would allow you to denormalize the database to improve query performance.</span></span>  
  
 <span data-ttu-id="43afb-111">При оценке размера базы данных производится оценка размера каждой из таблиц и сложение полученных значений.</span><span class="sxs-lookup"><span data-stu-id="43afb-111">To estimate the size of a database, estimate the size of each table individually and then add the values obtained.</span></span> <span data-ttu-id="43afb-112">Размер таблицы зависит от наличия у этой таблицы индексов и, если они есть, от их типов.</span><span class="sxs-lookup"><span data-stu-id="43afb-112">The size of a table depends on whether the table has indexes and, if they do, what type of indexes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43afb-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="43afb-113">In This Section</span></span>  
  
|<span data-ttu-id="43afb-114">Раздел</span><span class="sxs-lookup"><span data-stu-id="43afb-114">Topic</span></span>|<span data-ttu-id="43afb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="43afb-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="43afb-116">Оценка размера таблицы</span><span class="sxs-lookup"><span data-stu-id="43afb-116">Estimate the Size of a Table</span></span>](estimate-the-size-of-a-table.md)|<span data-ttu-id="43afb-117">Определяет шаги и вычисления для оценки места на диске, необходимого для хранения данных в таблице и связанных индексах.</span><span class="sxs-lookup"><span data-stu-id="43afb-117">Defines the steps and calculations needed to estimate the amount of space required to store the data in a table and associated indexes.</span></span>|  
|[<span data-ttu-id="43afb-118">Оценка размера кучи</span><span class="sxs-lookup"><span data-stu-id="43afb-118">Estimate the Size of a Heap</span></span>](estimate-the-size-of-a-heap.md)|<span data-ttu-id="43afb-119">Определяет шаги и вычисления для оценки места на диске, необходимого для хранения данных в куче.</span><span class="sxs-lookup"><span data-stu-id="43afb-119">Defines the steps and calculations needed to estimate the amount of space required to store the data in a heap.</span></span> <span data-ttu-id="43afb-120">Кучей называется таблица, не имеющая кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="43afb-120">A heap is a table that does not have a clustered index.</span></span>|  
|[<span data-ttu-id="43afb-121">Оценка размера кластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="43afb-121">Estimate the Size of a Clustered Index</span></span>](estimate-the-size-of-a-clustered-index.md)|<span data-ttu-id="43afb-122">Определяет шаги и вычисления, необходимые для оценки места на диске, необходимого для хранения данных в кластеризованном индексе.</span><span class="sxs-lookup"><span data-stu-id="43afb-122">Defines the steps and calculations needed to estimate the amount of space required to store the data in a clustered index.</span></span>|  
|[<span data-ttu-id="43afb-123">Оценка размера некластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="43afb-123">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)|<span data-ttu-id="43afb-124">Определяет шаги и вычисления для оценки места на диске, необходимого для хранения данных в некластеризованном индексе.</span><span class="sxs-lookup"><span data-stu-id="43afb-124">Defines the steps and calculations needed to estimate the amount of space required to store the data in a nonclustered index.</span></span>|  
  
  
