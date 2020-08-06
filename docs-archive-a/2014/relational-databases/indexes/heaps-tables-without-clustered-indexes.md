---
title: Кучи (таблицы без кластеризованных индексов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- heaps
ms.assetid: df5c4dfb-d372-4d0f-859a-a2d2533ee0d7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a39bac2e0352f2adc7749e980d5cc91044f8ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668322"
---
# <a name="heaps-tables-without-clustered-indexes"></a><span data-ttu-id="19c1e-102">Кучи (таблицы без кластеризованных индексов)</span><span class="sxs-lookup"><span data-stu-id="19c1e-102">Heaps (Tables without Clustered Indexes)</span></span>
  <span data-ttu-id="19c1e-103">Кучей является таблица без кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="19c1e-103">A heap is a table without a clustered index.</span></span> <span data-ttu-id="19c1e-104">Для таблиц, сохраненных как куча, может быть создан один или несколько некластеризованных индексов.</span><span class="sxs-lookup"><span data-stu-id="19c1e-104">One or more nonclustered indexes can be created on tables stored as a heap.</span></span> <span data-ttu-id="19c1e-105">Данные хранятся в куче без указания порядка.</span><span class="sxs-lookup"><span data-stu-id="19c1e-105">Data is stored in the heap without specifying an order.</span></span> <span data-ttu-id="19c1e-106">Обычно данные первоначально сохраняются в порядке, в котором строки вставлены в таблицу, но компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] может перемещать данные в куче для более эффективного хранения строк. Поэтому порядок данных нельзя прогнозировать.</span><span class="sxs-lookup"><span data-stu-id="19c1e-106">Usually data is initially stored in the order in which is the rows are inserted into the table, but the [!INCLUDE[ssDE](../../includes/ssde-md.md)] can move data around in the heap to store the rows efficiently; so the data order cannot be predicted.</span></span> <span data-ttu-id="19c1e-107">Чтобы гарантировать порядок строк, возвращаемых из кучи, необходимо использовать предложение `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="19c1e-107">To guarantee the order of rows returned from a heap, you must use the `ORDER BY` clause.</span></span> <span data-ttu-id="19c1e-108">Чтобы указать порядок хранения строк, подготовьте кластеризованный индекс для таблицы, чтобы таблица не была кучей.</span><span class="sxs-lookup"><span data-stu-id="19c1e-108">To specify the order for storage of the rows, create a clustered index on the table, so that the table is not a heap.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19c1e-109">Иногда бывают достаточные основания для того, чтобы оставить таблицу в виде кучи, не создавая кластеризованный индекс, однако эффективное использование куч требует высокой квалификации.</span><span class="sxs-lookup"><span data-stu-id="19c1e-109">There are sometimes good reasons to leave a table as a heap instead of creating a clustered index, but using heaps effectively is an advanced skill.</span></span> <span data-ttu-id="19c1e-110">Большинству таблиц следует создать кластеризованный индекс, если не существует веских оснований, чтобы оставить таблицу в виде кучи.</span><span class="sxs-lookup"><span data-stu-id="19c1e-110">Most tables should have a carefully chosen clustered index unless a good reason exists for leaving the table as a heap.</span></span>  
  
## <a name="when-to-use-a-heap"></a><span data-ttu-id="19c1e-111">Когда следует использовать кучу</span><span class="sxs-lookup"><span data-stu-id="19c1e-111">When to Use a Heap</span></span>  
 <span data-ttu-id="19c1e-112">Если таблица является кучей и не имеет кластеризованных индексов, требуется просмотреть всю таблицу (выполнить просмотр таблицы), чтобы найти любую строку.</span><span class="sxs-lookup"><span data-stu-id="19c1e-112">If a table is a heap and does not have any nonclustered indexes, then the entire table must be examined (a table scan) to find any row.</span></span> <span data-ttu-id="19c1e-113">Это приемлемо, если таблица очень мала, допустим, представляет собой список 12 региональных офисов компании.</span><span class="sxs-lookup"><span data-stu-id="19c1e-113">This can be acceptable when the table is tiny, such as a list of the 12 regional offices of a company.</span></span>  
  
 <span data-ttu-id="19c1e-114">Если таблица сохранена как куча, отдельные строки идентифицируются по ссылке на идентификатор строки (RID), состоящий из номера файла, номера страницы данных и слота на странице.</span><span class="sxs-lookup"><span data-stu-id="19c1e-114">When a table is stored as a heap, individual rows are identified by reference to a row identifier (RID) consisting of the file number, data page number, and slot on the page.</span></span> <span data-ttu-id="19c1e-115">Идентификатор строки является небольшой и эффективной структурой.</span><span class="sxs-lookup"><span data-stu-id="19c1e-115">The row id is a small and efficient structure.</span></span> <span data-ttu-id="19c1e-116">Иногда архитекторы данных используют кучи, если доступ к данным осуществляется только через некластеризованные индексы, а идентификатор RID меньше ключа кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="19c1e-116">Sometimes data architects use heaps when data is always accessed through nonclustered indexes and the RID is smaller than a clustered index key.</span></span>  
  
## <a name="when-not-to-use-a-heap"></a><span data-ttu-id="19c1e-117">Когда не нужно использовать кучу</span><span class="sxs-lookup"><span data-stu-id="19c1e-117">When Not to Use a Heap</span></span>  
 <span data-ttu-id="19c1e-118">Не следует использовать кучу, если данные часто возвращаются в отсортированном порядке.</span><span class="sxs-lookup"><span data-stu-id="19c1e-118">Do not use a heap when the data is frequently returned in a sorted order.</span></span> <span data-ttu-id="19c1e-119">Кластеризованный индекс для столбца сортировки поможет избежать операции сортировки.</span><span class="sxs-lookup"><span data-stu-id="19c1e-119">A clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="19c1e-120">Не используйте кучу для часто группируемых данных.</span><span class="sxs-lookup"><span data-stu-id="19c1e-120">Do not use a heap when the data is frequently grouped together.</span></span> <span data-ttu-id="19c1e-121">Данные необходимо сортировать перед группировкой, и кластеризованный индекс для столбца сортировки поможет избежать операции сортировки.</span><span class="sxs-lookup"><span data-stu-id="19c1e-121">Data must be sorted before it is grouped, and a clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="19c1e-122">Не следует использовать кучу, когда из таблицы часто запрашиваются диапазоны данных.</span><span class="sxs-lookup"><span data-stu-id="19c1e-122">Do not use a heap when ranges of data are frequently queried from the table.</span></span>  <span data-ttu-id="19c1e-123">Кластеризованный индекс для гистограммы диапазонов позволит избежать сортировки всей кучи.</span><span class="sxs-lookup"><span data-stu-id="19c1e-123">A clustered index on the range column will avoid sorting the entire heap.</span></span>  
  
 <span data-ttu-id="19c1e-124">Не используйте кучу, если некластеризованные индексы отсутствуют, а таблица большая.</span><span class="sxs-lookup"><span data-stu-id="19c1e-124">Do not use a heap when there are no nonclustered indexes and the table is large.</span></span> <span data-ttu-id="19c1e-125">В куче, чтобы можно было найти любую строку, должны считываться все строки кучи.</span><span class="sxs-lookup"><span data-stu-id="19c1e-125">In a heap, all rows of the heap must be read to find any row.</span></span>  
  
## <a name="managing-heaps"></a><span data-ttu-id="19c1e-126">Управление кучами</span><span class="sxs-lookup"><span data-stu-id="19c1e-126">Managing Heaps</span></span>  
 <span data-ttu-id="19c1e-127">Чтобы создать кучу, создайте таблицу без кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="19c1e-127">To create a heap, create a table without a clustered index.</span></span> <span data-ttu-id="19c1e-128">Если в таблице уже содержится кластеризованный индекс, удалите кластеризованный индекс, чтобы преобразовать таблицу в кучу.</span><span class="sxs-lookup"><span data-stu-id="19c1e-128">If a table already has a clustered index, drop the clustered index to return the table to a heap.</span></span>  
  
 <span data-ttu-id="19c1e-129">Чтобы удалить кучу, создайте кластеризованный индекс в ней.</span><span class="sxs-lookup"><span data-stu-id="19c1e-129">To remove a heap, create a clustered index on the heap.</span></span>  
  
 <span data-ttu-id="19c1e-130">Чтобы перестроить кучу с целью освобождения нерационально используемого пространства, создайте в ней кластеризованный индекс, а затем удалите его.</span><span class="sxs-lookup"><span data-stu-id="19c1e-130">To rebuild a heap to reclaim wasted space, create a clustered index on the heap, and then drop that clustered index.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="19c1e-131">Создание или удаление кластеризованных индексов требует перезаписи всей таблицы.</span><span class="sxs-lookup"><span data-stu-id="19c1e-131">Creating or dropping clustered indexes requires rewriting the entire table.</span></span> <span data-ttu-id="19c1e-132">Если у таблицы есть некластеризованные индексы, то все они должны быть созданы повторно при каждом изменении кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="19c1e-132">If the table has nonclustered indexes, all the nonclustered indexes must all be recreated whenever the clustered index is changed.</span></span> <span data-ttu-id="19c1e-133">Таким образом, для перехода с кучи на кластеризованный индекс и обратно может потребоваться продолжительное время и дополнительное место на диске — для переупорядочения данных в базе данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="19c1e-133">Therefore, changing from a heap to a clustered index structure or back can take a lot of time and require disk space for reordering data in tempdb.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="19c1e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="19c1e-134">Related Content</span></span>  
 [<span data-ttu-id="19c1e-135">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="19c1e-135">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="19c1e-136">DROP INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="19c1e-136">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="19c1e-137">Описание кластеризованных и некластеризованных индексов</span><span class="sxs-lookup"><span data-stu-id="19c1e-137">Clustered and Nonclustered Indexes Described</span></span>](clustered-and-nonclustered-indexes-described.md)  
  
  
