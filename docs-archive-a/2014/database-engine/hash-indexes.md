---
title: Хэш-индексы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f4bdc9c1-7922-4fac-8183-d11ec58fec4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8d1e3a5d92078cc2ec3fe7cd5b6d3fb5b47c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750127"
---
# <a name="hash-indexes"></a><span data-ttu-id="620bc-102">Хэш-индексы.</span><span class="sxs-lookup"><span data-stu-id="620bc-102">Hash Indexes</span></span>
  <span data-ttu-id="620bc-103">Индексы используются в качестве точек входа для таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="620bc-103">Indexes are used as entry points for memory-optimized tables.</span></span> <span data-ttu-id="620bc-104">Для считывания строк из таблицы требуется индекс, который определяет местоположение данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="620bc-104">Reading rows from a table requires an index to locate the data in memory.</span></span>  
  
 <span data-ttu-id="620bc-105">Хэш-индекс состоит из коллекции контейнеров, организованных в массив.</span><span class="sxs-lookup"><span data-stu-id="620bc-105">A hash index consists of a collection of buckets organized in an array.</span></span> <span data-ttu-id="620bc-106">Хэш-функция сопоставляет ключи индекса с соответствующими контейнерами в хэш-индексе.</span><span class="sxs-lookup"><span data-stu-id="620bc-106">A hash function maps index keys to corresponding buckets in the hash index.</span></span> <span data-ttu-id="620bc-107">На следующем рисунке показаны три ключа индекса, сопоставленные с тремя различными контейнерами в хэш-индексе.</span><span class="sxs-lookup"><span data-stu-id="620bc-107">The following figure shows three index keys that are mapped to three different buckets in the hash index.</span></span> <span data-ttu-id="620bc-108">Для наглядности хэш-функция называется f(x).</span><span class="sxs-lookup"><span data-stu-id="620bc-108">For illustration purposes the hash function name is f(x).</span></span>  
  
 <span data-ttu-id="620bc-109">![Ключи индекса, сопоставленные с различными контейнерами.](../../2014/database-engine/media/hekaton-tables-2.gif "Ключи индекса, сопоставленные с различными контейнерами.")</span><span class="sxs-lookup"><span data-stu-id="620bc-109">![Index keys mapped to different buckets.](../../2014/database-engine/media/hekaton-tables-2.gif "Index keys mapped to different buckets.")</span></span>  
  
 <span data-ttu-id="620bc-110">Функция, используемая для хэширования индексов, имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="620bc-110">The hashing function used for hash indexes has the following characteristics:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="620bc-111">имеет одну хэш-функцию, используемую для всех хэш-индексов.</span><span class="sxs-lookup"><span data-stu-id="620bc-111">has one hash function that is used for all hash indexes.</span></span>  
  
-   <span data-ttu-id="620bc-112">Хэш-функция является детерминированной.</span><span class="sxs-lookup"><span data-stu-id="620bc-112">The hash function is deterministic.</span></span> <span data-ttu-id="620bc-113">Один ключ индекса всегда связан с одним контейнером в хэш-индексе.</span><span class="sxs-lookup"><span data-stu-id="620bc-113">The same index key is always mapped to the same bucket in the hash index.</span></span>  
  
-   <span data-ttu-id="620bc-114">Несколько ключей индекса могут быть сопоставлены с одним и тем же хэш-контейнером индекса.</span><span class="sxs-lookup"><span data-stu-id="620bc-114">Multiple index keys may be mapped to the same hash bucket.</span></span>  
  
-   <span data-ttu-id="620bc-115">Хэш-функция сбалансирована, а это означает, что распределение значений ключей индекса, связанных с хэш-контейнерами, соответствует распределению Пуассона.</span><span class="sxs-lookup"><span data-stu-id="620bc-115">The hash function is balanced, meaning that the distribution of index key values over hash buckets typically follows a Poisson distribution.</span></span>  
  
     <span data-ttu-id="620bc-116">Распределение Пуассона не является равномерным.</span><span class="sxs-lookup"><span data-stu-id="620bc-116">Poisson distribution is not an even distribution.</span></span> <span data-ttu-id="620bc-117">Значения ключа индекса не распределяются в хэш-контейнерах равномерно.</span><span class="sxs-lookup"><span data-stu-id="620bc-117">Index key values are not evenly distributed in the hash buckets.</span></span> <span data-ttu-id="620bc-118">Например, распределение Пуассона разных ключей индекса *n* по хэш-контейнерам *n* приводит к созданию примерно трети пустых контейнеров, трети контейнеров, содержащих один ключ индекса, и трети, содержащей по два ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="620bc-118">For example, a Poisson distribution of *n* distinct index keys over *n* hash buckets results in approximately one third empty buckets, one third of the buckets containing one index key, and the other third containing two index keys.</span></span> <span data-ttu-id="620bc-119">Небольшое число контейнеров всегда будет содержать более двух ключей.</span><span class="sxs-lookup"><span data-stu-id="620bc-119">A small number of buckets will contain more than two keys.</span></span>  
  
 <span data-ttu-id="620bc-120">Если два ключа индекса сопоставляются с одним хэш-контейнером, происходит конфликт хэша.</span><span class="sxs-lookup"><span data-stu-id="620bc-120">If two index keys are mapped to the same hash bucket, there is a hash collision.</span></span> <span data-ttu-id="620bc-121">Большое число конфликтов хэша может оказывать негативное влияние на операции чтения.</span><span class="sxs-lookup"><span data-stu-id="620bc-121">A large number of hash collisions can have a performance impact on read operations.</span></span>  
  
 <span data-ttu-id="620bc-122">Структура хэш-индекса в памяти состоит из массива указателей памяти.</span><span class="sxs-lookup"><span data-stu-id="620bc-122">The in-memory hash index structure consists of an array of memory pointers.</span></span> <span data-ttu-id="620bc-123">Каждый контейнер связан с определенным смещением в этом массиве.</span><span class="sxs-lookup"><span data-stu-id="620bc-123">Each bucket maps to an offset in this array.</span></span> <span data-ttu-id="620bc-124">Каждый контейнер в массиве указывает на первую строку в этом хэш-контейнере.</span><span class="sxs-lookup"><span data-stu-id="620bc-124">Each bucket in the array points to the first row in that hash bucket.</span></span> <span data-ttu-id="620bc-125">Каждая строка в контейнере указывает на следующую строку, образуя таким образом цепочку строк для каждого хэш-контейнера, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="620bc-125">Each row in the bucket points to the next row, thus resulting in a chain of rows for each hash bucket, as illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="620bc-126">![Структура хэш-индекса в памяти.](../../2014/database-engine/media/hekaton-tables-3.gif "Структура хэш-индекса в памяти.")</span><span class="sxs-lookup"><span data-stu-id="620bc-126">![The in-memory hash index structure.](../../2014/database-engine/media/hekaton-tables-3.gif "The in-memory hash index structure.")</span></span>  
  
 <span data-ttu-id="620bc-127">На рисунке изображены три контейнера со строками.</span><span class="sxs-lookup"><span data-stu-id="620bc-127">The figure has three buckets with rows.</span></span> <span data-ttu-id="620bc-128">Второй контейнер сверху содержит три красные строки.</span><span class="sxs-lookup"><span data-stu-id="620bc-128">The second bucket from the top contains the three red rows.</span></span> <span data-ttu-id="620bc-129">Четвертый контейнер — одну голубую строку.</span><span class="sxs-lookup"><span data-stu-id="620bc-129">The fourth bucket contains the single blue row.</span></span> <span data-ttu-id="620bc-130">Нижний контейнер содержит две зеленые строки.</span><span class="sxs-lookup"><span data-stu-id="620bc-130">The bottom bucket contains the two green rows.</span></span> <span data-ttu-id="620bc-131">Это могут быть разные версии одной строки.</span><span class="sxs-lookup"><span data-stu-id="620bc-131">These could be different versions of the same row.</span></span>  
  
 <span data-ttu-id="620bc-132">Дополнительные сведения об индексах оптимизированных для памяти таблиц см. в разделе [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="620bc-132">For more information about indexes for memory-optimized tables, see [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620bc-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="620bc-133">See Also</span></span>  
 [<span data-ttu-id="620bc-134">Индексы для оптимизированных для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="620bc-134">Indexes on Memory-Optimized Tables</span></span>](../../2014/database-engine/indexes-on-memory-optimized-tables.md)  
  
  
