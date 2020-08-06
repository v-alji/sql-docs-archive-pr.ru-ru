---
title: Размер строк и таблицы для таблиц, оптимизированных для памяти | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b0a248a4-4488-4cc8-89fc-46906a8c24a1
author: rothja
ms.author: jroth
ms.openlocfilehash: 74cc40b7d1f2d0132d79d1e9ae15c2321ac9b74a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750947"
---
# <a name="table-and-row-size-in-memory-optimized-tables"></a><span data-ttu-id="55b34-102">Размер строк и таблицы для таблиц, оптимизированных для памяти</span><span class="sxs-lookup"><span data-stu-id="55b34-102">Table and Row Size in Memory-Optimized Tables</span></span>
  <span data-ttu-id="55b34-103">Таблица, оптимизированная для памяти, представляет собой набор строк, а также индексов, которые содержат указатели на строки.</span><span class="sxs-lookup"><span data-stu-id="55b34-103">A memory-optimized table consists of a collection of rows and indexes that contain pointers to rows.</span></span> <span data-ttu-id="55b34-104">В таблице с оптимизацией для памяти строки не могут быть длиннее 8060 байт.</span><span class="sxs-lookup"><span data-stu-id="55b34-104">In a memory-optimized table, rows cannot be longer than 8,060 bytes.</span></span> <span data-ttu-id="55b34-105">Основные сведения о размере таблицы с оптимизацией для памяти помогут понять, имеет ли компьютер достаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="55b34-105">Understanding the size of a memory-optimized table will help you understand if your computer has enough memory.</span></span>  
  
 <span data-ttu-id="55b34-106">Существуют две причины для вычисления размера таблиц и строк.</span><span class="sxs-lookup"><span data-stu-id="55b34-106">There are two reasons for computing table and row size:</span></span>  
  
-   <span data-ttu-id="55b34-107">Какой объем памяти используется таблицей?</span><span class="sxs-lookup"><span data-stu-id="55b34-107">How much memory does a table use?</span></span>  
  
    -   <span data-ttu-id="55b34-108">Объем используемой таблицей памяти невозможно подсчитать точно.</span><span class="sxs-lookup"><span data-stu-id="55b34-108">The amount of memory used by the table cannot be calculated exactly.</span></span> <span data-ttu-id="55b34-109">На объем используемой памяти влияет множество факторов.</span><span class="sxs-lookup"><span data-stu-id="55b34-109">Many factors affect the amount of memory used.</span></span> <span data-ttu-id="55b34-110">Это такие факторы, как постраничное выделение места в памяти, размещение, кэширование и заполнение.</span><span class="sxs-lookup"><span data-stu-id="55b34-110">Factors such as page-based memory allocation, locality, caching, and padding.</span></span> <span data-ttu-id="55b34-111">Кроме того, несколько версий строк, которые имеют активные связанные транзакции либо ожидают сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="55b34-111">Also, multiple versions of rows that either have active transactions associated or that are waiting for garbage collection.</span></span>  
  
    -   <span data-ttu-id="55b34-112">Минимальный размер, необходимый для данных и индексов в таблице, определяется вычислением для [размера таблицы], о котором рассказывается ниже.</span><span class="sxs-lookup"><span data-stu-id="55b34-112">The minimum size required for the data and indexes in the table is given by the calculation for [table size], discussed below.</span></span>  
  
    -   <span data-ttu-id="55b34-113">Вычисление используемой памяти в самом лучшем случае может быть выполнено лишь приближенно, поэтому рекомендуется включить планирование вместимости в планы разработки.</span><span class="sxs-lookup"><span data-stu-id="55b34-113">Calculating memory use is at best an approximation and you are advised to include capacity planning in your deployment plans.</span></span>  
  
-   <span data-ttu-id="55b34-114">Каков размер строки данных, и укладывается ли он в ограничение размера строки 8060 байт?</span><span class="sxs-lookup"><span data-stu-id="55b34-114">The data size of a row, and does it fit in the 8,060 byte row size limitation?</span></span> <span data-ttu-id="55b34-115">Чтобы получить ответ на эти вопросы, используйте вычисление для [размера текста строки], о котором рассказывается ниже.</span><span class="sxs-lookup"><span data-stu-id="55b34-115">To answer these questions, use the computation for [row body size], discussed below.</span></span>  
  
 <span data-ttu-id="55b34-116">На следующей схеме показана таблица с индексами и строками, которые в свою очередь содержат заголовки и текст:</span><span class="sxs-lookup"><span data-stu-id="55b34-116">The following figure illustrates a table with indexes and rows, which in turn have row headers and bodies:</span></span>  
  
 <span data-ttu-id="55b34-117">![Оптимизированная для памяти таблица.](../../database-engine/media/hekaton-guide-1.gif "Оптимизированная для памяти таблица.")</span><span class="sxs-lookup"><span data-stu-id="55b34-117">![Memory optimized table.](../../database-engine/media/hekaton-guide-1.gif "Memory optimized table.")</span></span>  
<span data-ttu-id="55b34-118">Таблица, оптимизированная для памяти, состоящая из индексов и строк.</span><span class="sxs-lookup"><span data-stu-id="55b34-118">Memory-optimized table, consisting of indexes and rows.</span></span>  
  
 <span data-ttu-id="55b34-119">Размер, занимаемый таблицей в памяти (в байтах) вычисляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="55b34-119">The in-memory size of a table, in bytes, is computed as follows:</span></span>  
  
```  
[table size] = [size of index 1] + ... + [size of index n] + ([row size] * [row count])  
```  
  
 <span data-ttu-id="55b34-120">Размер хэш-индекса фиксируется на момент создания таблицы и зависит от фактического числа контейнеров.</span><span class="sxs-lookup"><span data-stu-id="55b34-120">The size of a hash index is fixed at table creation time and depends on the actual bucket count.</span></span> <span data-ttu-id="55b34-121">Значение bucket_count, указанное спецификацией индекса, округляется в сторону увеличения до ближайшей степени числа 2 для получения [фактического числа контейнеров].</span><span class="sxs-lookup"><span data-stu-id="55b34-121">The bucket_count specified with the index specification is rounded up to the nearest power of 2 to obtain the [actual bucket count].</span></span> <span data-ttu-id="55b34-122">Например, если заданное число bucket_count равно 100000, то [фактическое число контейнеров] для индекса составляет 131072.</span><span class="sxs-lookup"><span data-stu-id="55b34-122">For example, if the specified bucket_count is 100000, the [actual bucket count] for the index is 131072.</span></span>  
  
```  
[hash index size] = 8 * [actual bucket count]  
```  
  
 <span data-ttu-id="55b34-123">Размер строки вычисляется путем сложения значений для заголовка и текста:</span><span class="sxs-lookup"><span data-stu-id="55b34-123">The row size is computed by adding the header and the body:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices]  
```  
  
 <span data-ttu-id="55b34-124">**Размер текста строки**</span><span class="sxs-lookup"><span data-stu-id="55b34-124">**Row body size**</span></span>  
  
 <span data-ttu-id="55b34-125">Вычисление [размера текста строки] демонстрируется в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="55b34-125">The calculation of [row body size] is discussed in the following table.</span></span>  
  
 <span data-ttu-id="55b34-126">Размер текста строки вычисляется двумя способами: вычисляемый размер и фактический размер.</span><span class="sxs-lookup"><span data-stu-id="55b34-126">There are two different computations for row body size: computed size and the actual size:</span></span>  
  
-   <span data-ttu-id="55b34-127">Вычисляемый размер, далее [вычисляемый размер строки текста], используется для того, чтобы определить, не превышает ли размер строки ограничение в 8060 байт.</span><span class="sxs-lookup"><span data-stu-id="55b34-127">The computed size, denoted with [computed row body size], is used to determine if the row size limitation of 8,060 bytes is exceeded.</span></span>  
  
-   <span data-ttu-id="55b34-128">Фактический размер, далее [фактический размер строки текста], представляет собой фактический размер хранилища текста строки в памяти и в файле контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="55b34-128">The actual size, denoted with [actual row body size], is the actual storage size of the row body in memory and in the checkpoint files.</span></span>  
  
 <span data-ttu-id="55b34-129">Оба показателя [вычисляемый размер строки текста] и [фактический размер строки текста] вычисляются аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="55b34-129">Both [computed row body size] and [actual row body size] are calculated similarly.</span></span> <span data-ttu-id="55b34-130">Отличается только вычисление размера столбцов (n)varchar(I) и столбцов varbinary (I), как показано в нижней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="55b34-130">The only difference is the calculation of the size of (n)varchar(i) and varbinary(i) columns, as reflected at the bottom of the following table.</span></span> <span data-ttu-id="55b34-131">Вычисляемый размер строки использует в качестве размера столбца декларируемый размер *i* , тогда как фактический размер строки использует фактический размер данных.</span><span class="sxs-lookup"><span data-stu-id="55b34-131">The computed row body size uses the declared size *i* as the size of the column, while the actual row body size uses the actual size of the data.</span></span>  
  
 <span data-ttu-id="55b34-132">В следующей таблице описано вычисление размера текста строки как [фактический размер текста строки] = SUM([размер мелких типов]) + 2 + 2 \* [число столбцов глубокого типа].</span><span class="sxs-lookup"><span data-stu-id="55b34-132">The following table describes the calculation of the row body size, given as [actual row body size] = SUM([size of shallow types]) + 2 + 2 \* [number of deep type columns].</span></span>  
  
|<span data-ttu-id="55b34-133">Section</span><span class="sxs-lookup"><span data-stu-id="55b34-133">Section</span></span>|<span data-ttu-id="55b34-134">Размер</span><span class="sxs-lookup"><span data-stu-id="55b34-134">Size</span></span>|<span data-ttu-id="55b34-135">Комментарии</span><span class="sxs-lookup"><span data-stu-id="55b34-135">Comments</span></span>|  
|-------------|----------|--------------|  
|<span data-ttu-id="55b34-136">Столбцы поверхностных типов</span><span class="sxs-lookup"><span data-stu-id="55b34-136">Shallow type columns</span></span>|<span data-ttu-id="55b34-137">SUM [размер поверхностных типов]</span><span class="sxs-lookup"><span data-stu-id="55b34-137">SUM([size of shallow types])</span></span><br /><br /> <span data-ttu-id="55b34-138">**Размеры отдельных типов:**</span><span class="sxs-lookup"><span data-stu-id="55b34-138">**Size of the individual types is as follows:**</span></span><br /><br /> <span data-ttu-id="55b34-139">Bit &#124; 1</span><span class="sxs-lookup"><span data-stu-id="55b34-139">Bit &#124; 1</span></span><br /><br /> <span data-ttu-id="55b34-140">Tinyint &#124; 1</span><span class="sxs-lookup"><span data-stu-id="55b34-140">Tinyint &#124; 1</span></span><br /><br /> <span data-ttu-id="55b34-141">Smallint &#124; 2</span><span class="sxs-lookup"><span data-stu-id="55b34-141">Smallint &#124; 2</span></span><br /><br /> <span data-ttu-id="55b34-142">Int &#124; 4</span><span class="sxs-lookup"><span data-stu-id="55b34-142">Int &#124; 4</span></span><br /><br /> <span data-ttu-id="55b34-143">Real &#124; 4</span><span class="sxs-lookup"><span data-stu-id="55b34-143">Real &#124; 4</span></span><br /><br /> <span data-ttu-id="55b34-144">Smalldatetime &#124; 4</span><span class="sxs-lookup"><span data-stu-id="55b34-144">Smalldatetime &#124; 4</span></span><br /><br /> <span data-ttu-id="55b34-145">Smallmoney &#124; 4</span><span class="sxs-lookup"><span data-stu-id="55b34-145">Smallmoney &#124; 4</span></span><br /><br /> <span data-ttu-id="55b34-146">Bigint &#124; 8</span><span class="sxs-lookup"><span data-stu-id="55b34-146">Bigint &#124; 8</span></span><br /><br /> <span data-ttu-id="55b34-147">Datetime &#124; 8</span><span class="sxs-lookup"><span data-stu-id="55b34-147">Datetime &#124; 8</span></span><br /><br /> <span data-ttu-id="55b34-148">Datetime2 &#124; 8</span><span class="sxs-lookup"><span data-stu-id="55b34-148">Datetime2 &#124; 8</span></span><br /><br /> <span data-ttu-id="55b34-149">Float 8</span><span class="sxs-lookup"><span data-stu-id="55b34-149">Float 8</span></span><br /><br /> <span data-ttu-id="55b34-150">Money 8</span><span class="sxs-lookup"><span data-stu-id="55b34-150">Money 8</span></span><br /><br /> <span data-ttu-id="55b34-151">Numeric (точность <= 18) &#124; 8</span><span class="sxs-lookup"><span data-stu-id="55b34-151">Numeric (precision <=18) &#124; 8</span></span><br /><br /> <span data-ttu-id="55b34-152">Time &#124; 8</span><span class="sxs-lookup"><span data-stu-id="55b34-152">Time &#124; 8</span></span><br /><br /> <span data-ttu-id="55b34-153">Numeric (точность>18) &#124; 16</span><span class="sxs-lookup"><span data-stu-id="55b34-153">Numeric(precision>18) &#124; 16</span></span><br /><br /> <span data-ttu-id="55b34-154">Uniqueidentifier &#124; 16</span><span class="sxs-lookup"><span data-stu-id="55b34-154">Uniqueidentifier &#124; 16</span></span>||  
|<span data-ttu-id="55b34-155">Заполнение столбца поверхностного типа</span><span class="sxs-lookup"><span data-stu-id="55b34-155">Shallow column padding</span></span>|<span data-ttu-id="55b34-156">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="55b34-156">Possible values are:</span></span><br /><br /> <span data-ttu-id="55b34-157">1, если в таблице присутствуют столбцы глубоких типов, а общий размер данных в столбцах поверхностного типа является нечетным числом.</span><span class="sxs-lookup"><span data-stu-id="55b34-157">1 if there are deep type columns and the total data size of the shallow columns is as odd number.</span></span><br /><br /> <span data-ttu-id="55b34-158">0 в остальных случаях</span><span class="sxs-lookup"><span data-stu-id="55b34-158">0 otherwise</span></span>|<span data-ttu-id="55b34-159">Глубокие типы — это типы (var)binary и (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="55b34-159">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="55b34-160">Массив смещений для столбцов глубоких типов</span><span class="sxs-lookup"><span data-stu-id="55b34-160">Offset array for deep type columns</span></span>|<span data-ttu-id="55b34-161">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="55b34-161">Possible values are:</span></span><br /><br /> <span data-ttu-id="55b34-162">0, если в таблице нет столбцов глубоких типов</span><span class="sxs-lookup"><span data-stu-id="55b34-162">0 if there are no deep type columns</span></span><br /><br /> <span data-ttu-id="55b34-163">2 + 2 \* [количество столбцов глубоких типов] во всех остальных случаях</span><span class="sxs-lookup"><span data-stu-id="55b34-163">2 + 2 \* [number of deep type columns] otherwise</span></span>|<span data-ttu-id="55b34-164">Глубокие типы — это типы (var)binary и (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="55b34-164">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="55b34-165">Массив значений NULL</span><span class="sxs-lookup"><span data-stu-id="55b34-165">NULL array</span></span>|<span data-ttu-id="55b34-166">[количество столбцов, в которых допустимы значения NULL] / 8, с округлением в сторону увеличения до целого числа байт.</span><span class="sxs-lookup"><span data-stu-id="55b34-166">[number of nullable columns] / 8, rounded up to full bytes.</span></span>|<span data-ttu-id="55b34-167">Массив содержит один бит для каждого столбца, допускающего значения NULL.</span><span class="sxs-lookup"><span data-stu-id="55b34-167">The array has one bit per nullable column.</span></span> <span data-ttu-id="55b34-168">Эта величина округляется в сторону увеличения до целого числа байт.</span><span class="sxs-lookup"><span data-stu-id="55b34-168">This is rounded up to full bytes.</span></span>|  
|<span data-ttu-id="55b34-169">Заполнение массива значений NULL</span><span class="sxs-lookup"><span data-stu-id="55b34-169">NULL array padding</span></span>|<span data-ttu-id="55b34-170">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="55b34-170">Possible values are:</span></span><br /><br /> <span data-ttu-id="55b34-171">1, если в таблице имеются столбцы глубоких типов данных и размер массива значений NULL равен нечетному числу байтов.</span><span class="sxs-lookup"><span data-stu-id="55b34-171">1 if there are deep type columns and the size of the NULL array is an odd number of bytes.</span></span><br /><br /> <span data-ttu-id="55b34-172">0 в остальных случаях</span><span class="sxs-lookup"><span data-stu-id="55b34-172">0 otherwise</span></span>|<span data-ttu-id="55b34-173">Глубокие типы — это типы (var)binary и (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="55b34-173">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="55b34-174">Заполнение</span><span class="sxs-lookup"><span data-stu-id="55b34-174">Padding</span></span>|<span data-ttu-id="55b34-175">Если в таблице нет столбцов глубоких типов: 0</span><span class="sxs-lookup"><span data-stu-id="55b34-175">If there are no deep type columns: 0</span></span><br /><br /> <span data-ttu-id="55b34-176">Если есть столбцы глубоких типов данных, добавляется 0–7 байт заполнения, исходя из наибольшего выравнивания, требующегося для столбцов поверхностных данных.</span><span class="sxs-lookup"><span data-stu-id="55b34-176">If there are deep type columns, 0-7 bytes of padding is added, based on the largest alignment required by a shallow column.</span></span> <span data-ttu-id="55b34-177">Каждый столбец поверхностных типов требует выравнивания, равного его размеру (как показано в документе выше), за исключением столбцов GUID, которые требуют выравнивания на 1 байт (а не на 16), и числовых столбцов, которые всегда требуют выравнивания 8 байт (ни в коем случае не 16).</span><span class="sxs-lookup"><span data-stu-id="55b34-177">Each shallow column requires alignment equal to its size as documented above, except that GUID columns need alignment of 1 byte (not 16) and numeric columns always need alignment of 8 bytes (never 16).</span></span> <span data-ttu-id="55b34-178">Используется наибольшее требование выравнивания среди всех столбцов поверхностных типов, и заполнение 0–7 байт добавляется таким образом, чтобы общий размер на этот момент (без столбцов глубоких типов) был кратным числу необходимых выравниваний.</span><span class="sxs-lookup"><span data-stu-id="55b34-178">The largest alignment requirement among all shallow columns is used, and 0-7 bytes of padding is added in such a way that the total size so far (without the deep type columns) is a multiple of the required alignment.</span></span>|<span data-ttu-id="55b34-179">Глубокие типы — это типы (var)binary и (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="55b34-179">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="55b34-180">Столбцы глубоких типов фиксированной длины</span><span class="sxs-lookup"><span data-stu-id="55b34-180">Fixed-length deep type columns</span></span>|<span data-ttu-id="55b34-181">SUM ([размер столбцов глубоких типов фиксированной длины])</span><span class="sxs-lookup"><span data-stu-id="55b34-181">SUM([size of fixed length deep type columns])</span></span><br /><br /> <span data-ttu-id="55b34-182">Размер каждого столбца составляет:</span><span class="sxs-lookup"><span data-stu-id="55b34-182">The size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="55b34-183">i для типов char(i) и binary(i).</span><span class="sxs-lookup"><span data-stu-id="55b34-183">i for char(i) and binary(i).</span></span><br /><br /> <span data-ttu-id="55b34-184">2 \* i для типа nchar(i)</span><span class="sxs-lookup"><span data-stu-id="55b34-184">2 \* i for nchar(i)</span></span>|<span data-ttu-id="55b34-185">Столбцы глубоких типов данных фиксированной длины — это столбцы типов char(i), nchar(i) или binary(i).</span><span class="sxs-lookup"><span data-stu-id="55b34-185">Fixed-length deep type columns are columns of type char(i), nchar(i), or binary(i).</span></span>|  
|<span data-ttu-id="55b34-186">Столбцы глубоких типов данных переменной длины [вычисляемый размер]</span><span class="sxs-lookup"><span data-stu-id="55b34-186">Variable length deep type columns [computed size]</span></span>|<span data-ttu-id="55b34-187">SUM([вычисляемый размер столбцов глубоких типов данных переменной длины])</span><span class="sxs-lookup"><span data-stu-id="55b34-187">SUM([computed size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="55b34-188">вычисляемый размер каждого столбца составляет:</span><span class="sxs-lookup"><span data-stu-id="55b34-188">The computed size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="55b34-189">i для типов varchar(i) и varbinary(i)</span><span class="sxs-lookup"><span data-stu-id="55b34-189">i for varchar(i) and varbinary(i)</span></span><br /><br /> <span data-ttu-id="55b34-190">2 \* i для типа nvarchar(i)</span><span class="sxs-lookup"><span data-stu-id="55b34-190">2 \* i for nvarchar(i)</span></span>|<span data-ttu-id="55b34-191">Эта строка применяется только к [вычисляемому размеру текста строки]</span><span class="sxs-lookup"><span data-stu-id="55b34-191">This row only applied to [computed row body size].</span></span><br /><br /> <span data-ttu-id="55b34-192">Столбцы глубоких типов переменной длины — это столбцы типов varchar(i), nvarchar(i) или varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="55b34-192">Variable-length deep type columns are columns of type varchar(i), nvarchar(i), or varbinary(i).</span></span> <span data-ttu-id="55b34-193">вычисляемый размер определяется максимальной длиной (i) столбца.</span><span class="sxs-lookup"><span data-stu-id="55b34-193">The computed size is determined by the max length (i) of the column.</span></span>|  
|<span data-ttu-id="55b34-194">Столбцы глубоких типов данных переменной длины [фактический размер]</span><span class="sxs-lookup"><span data-stu-id="55b34-194">Variable length deep type columns [actual size]</span></span>|<span data-ttu-id="55b34-195">SUM([фактический размер столбцов глубоких типов данных переменной длины])</span><span class="sxs-lookup"><span data-stu-id="55b34-195">SUM([actual size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="55b34-196">Фактический размер каждого столбца составляет:</span><span class="sxs-lookup"><span data-stu-id="55b34-196">The actual size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="55b34-197">n, где n — количество символов, хранящихся в столбце, для типа varchar(i).</span><span class="sxs-lookup"><span data-stu-id="55b34-197">n, where n is the number of characters stored in the column, for varchar(i).</span></span><br /><br /> <span data-ttu-id="55b34-198">2 \* n, где n — количество символов, хранящихся в столбце, для типа nvarchar(i).</span><span class="sxs-lookup"><span data-stu-id="55b34-198">2 \* n, where n is the number of characters stored in the column, for nvarchar(i).</span></span><br /><br /> <span data-ttu-id="55b34-199">n, где n — число байтов, хранящихся в столбце, для типа varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="55b34-199">n, where n is the number of bytes stored in the column, for varbinary(i).</span></span>|<span data-ttu-id="55b34-200">Эта строка применяется только к [фактическому размеру текста строки].</span><span class="sxs-lookup"><span data-stu-id="55b34-200">This row only applied to [actual row body size].</span></span><br /><br /> <span data-ttu-id="55b34-201">Фактический размер определяется данными, которые хранятся в столбцах в данной строке.</span><span class="sxs-lookup"><span data-stu-id="55b34-201">The actual size is determined by the data stored in the columns in the row.</span></span>|  
  
##  <a name="row-structure"></a><a name="bkmk_RowStructure"></a><span data-ttu-id="55b34-202">Структура строки</span><span class="sxs-lookup"><span data-stu-id="55b34-202">Row Structure</span></span>  
 <span data-ttu-id="55b34-203">Строки в таблице, оптимизированной для памяти, включают следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="55b34-203">The rows in a memory-optimized table have the following components:</span></span>  
  
-   <span data-ttu-id="55b34-204">Заголовок строки содержит метку времени, необходимую для управления версиями строки.</span><span class="sxs-lookup"><span data-stu-id="55b34-204">The row header contains the timestamp necessary to implement row versioning.</span></span> <span data-ttu-id="55b34-205">Заголовок строки также содержит указатель индекса, который позволяет реализовать цепочку строк в хэш-контейнере (описано выше).</span><span class="sxs-lookup"><span data-stu-id="55b34-205">The row header also contains the index pointer to implement the row chaining in the hash buckets (described above).</span></span>  
  
-   <span data-ttu-id="55b34-206">Текст строки содержит фактические данные столбцов, которые включают некоторые вспомогательные сведения, такие как массив значений NULL для столбцов, допускающих значение NULL, и массив смещений для типов данных с переменной длиной.</span><span class="sxs-lookup"><span data-stu-id="55b34-206">The row body contains the actual column data, which includes some auxiliary information like the null array for nullable columns and the offset array for variable-length data types.</span></span>  
  
 <span data-ttu-id="55b34-207">На следующем рисунке показана структура строк для таблицы с двумя индексами.</span><span class="sxs-lookup"><span data-stu-id="55b34-207">The following figure illustrates the row structure for a table that has two indexes:</span></span>  
  
 <span data-ttu-id="55b34-208">![Структура строк для таблицы с двумя индексами.](../../database-engine/media/hekaton-tables-4.gif "Структура строк для таблицы с двумя индексами.")</span><span class="sxs-lookup"><span data-stu-id="55b34-208">![Row structure for a table that has two indexes.](../../database-engine/media/hekaton-tables-4.gif "Row structure for a table that has two indexes.")</span></span>  
  
 <span data-ttu-id="55b34-209">Метки времени начала и конца показывают период, в котором определенная версия строки является допустимой.</span><span class="sxs-lookup"><span data-stu-id="55b34-209">The begin and end timestamps indicate the period in which a particular row version is valid.</span></span> <span data-ttu-id="55b34-210">Транзакции, запускаемые в данном интервале, могут видеть эту версию строки.</span><span class="sxs-lookup"><span data-stu-id="55b34-210">Transactions that start in this interval can see this row version.</span></span> <span data-ttu-id="55b34-211">Дополнительные сведения см. в разделе [Транзакции в таблицах, оптимизированных для памяти](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="55b34-211">For more details see [Transactions in Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="55b34-212">Указатели индекса указывают на следующую строку в цепочке, принадлежащей хэш-контейнеру.</span><span class="sxs-lookup"><span data-stu-id="55b34-212">The index pointers point to the next row in the chain belonging to the hash bucket.</span></span> <span data-ttu-id="55b34-213">На следующем рисунке показана структура таблицы с двумя столбцами (имя, город) и двумя индексами, один для столбца name и второй для столбца city.</span><span class="sxs-lookup"><span data-stu-id="55b34-213">The following figure illustrates the structure of a table with two columns (name, city), and with two indexes, one on the column name, and one on the column city.</span></span>  
  
 <span data-ttu-id="55b34-214">![Структура таблицы с двумя столбцами и индексами.](../../database-engine/media/hekaton-tables-5.gif "Структура таблицы с двумя столбцами и индексами.")</span><span class="sxs-lookup"><span data-stu-id="55b34-214">![Structure of a table with two columns and indexes.](../../database-engine/media/hekaton-tables-5.gif "Structure of a table with two columns and indexes.")</span></span>  
  
 <span data-ttu-id="55b34-215">На этом рисунке имена Джон и Джейн хэшированы на первый контейнер.</span><span class="sxs-lookup"><span data-stu-id="55b34-215">In this figure, the names John and Jane are hashed to the first bucket.</span></span> <span data-ttu-id="55b34-216">Сьюзан хэширована на втором контейнере.</span><span class="sxs-lookup"><span data-stu-id="55b34-216">Susan is hashed to the second bucket.</span></span> <span data-ttu-id="55b34-217">Города Пекин и Богота хэшированы на первом контейнере.</span><span class="sxs-lookup"><span data-stu-id="55b34-217">The cities Beijing and Bogota are hashed to the first bucket.</span></span> <span data-ttu-id="55b34-218">Париж и Прага хэшированы на втором контейнере.</span><span class="sxs-lookup"><span data-stu-id="55b34-218">Paris and Prague are hashed to the second bucket.</span></span>  
  
 <span data-ttu-id="55b34-219">Таким образом, цепочки для хэш-индекса по именам выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="55b34-219">Thus, the chains for the hash index on name are as follows:</span></span>  
  
-   <span data-ttu-id="55b34-220">Первый контейнер: (Джон, Пекин); (Джон, Париж); (Джейн, Прага)</span><span class="sxs-lookup"><span data-stu-id="55b34-220">First bucket: (John, Beijing); (John, Paris); (Jane, Prague)</span></span>  
  
-   <span data-ttu-id="55b34-221">Второй контейнер: (Сьюзан, Богота)</span><span class="sxs-lookup"><span data-stu-id="55b34-221">Second bucket: (Susan, Bogota)</span></span>  
  
 <span data-ttu-id="55b34-222">Цепочки для индекса по городам выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="55b34-222">The chains for the index on city are as follows:</span></span>  
  
-   <span data-ttu-id="55b34-223">Первый контейнер: (Джон Пекин), (Сьюзан, Богота)</span><span class="sxs-lookup"><span data-stu-id="55b34-223">First bucket: (John, Beijing), (Susan, Bogota)</span></span>  
  
-   <span data-ttu-id="55b34-224">Второй контейнер: (Джон, Париж), (Джейн, Прага)</span><span class="sxs-lookup"><span data-stu-id="55b34-224">Second bucket: (John, Paris), (Jane, Prague)</span></span>  
  
 <span data-ttu-id="55b34-225">Метка времени окончания &#x221e; (бесконечность) указывает, что это текущая допустимая версия строки.</span><span class="sxs-lookup"><span data-stu-id="55b34-225">An end timestamp &#x221e; (infinity) indicates that this is the currently valid version of the row.</span></span> <span data-ttu-id="55b34-226">Строка была обновлена или удалена с того момента, как была записана эта версия.</span><span class="sxs-lookup"><span data-stu-id="55b34-226">The row has not been updated or deleted since this row version was written.</span></span>  
  
 <span data-ttu-id="55b34-227">Для времени больше 200 таблица содержит следующие строки.</span><span class="sxs-lookup"><span data-stu-id="55b34-227">For a time greater than 200, the table contains the following rows:</span></span>  
  
|<span data-ttu-id="55b34-228">Имя</span><span class="sxs-lookup"><span data-stu-id="55b34-228">Name</span></span>|<span data-ttu-id="55b34-229">Город</span><span class="sxs-lookup"><span data-stu-id="55b34-229">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="55b34-230">Джон</span><span class="sxs-lookup"><span data-stu-id="55b34-230">John</span></span>|<span data-ttu-id="55b34-231">Пекин</span><span class="sxs-lookup"><span data-stu-id="55b34-231">Beijing</span></span>|  
|<span data-ttu-id="55b34-232">Джейн</span><span class="sxs-lookup"><span data-stu-id="55b34-232">Jane</span></span>|<span data-ttu-id="55b34-233">Прага</span><span class="sxs-lookup"><span data-stu-id="55b34-233">Prague</span></span>|  
  
 <span data-ttu-id="55b34-234">Однако любая активная транзакция с начальным временем 100 увидит следующую версию таблицы.</span><span class="sxs-lookup"><span data-stu-id="55b34-234">However, any active transaction with begin time 100 will see the following version of the table:</span></span>  
  
|<span data-ttu-id="55b34-235">Имя</span><span class="sxs-lookup"><span data-stu-id="55b34-235">Name</span></span>|<span data-ttu-id="55b34-236">Город</span><span class="sxs-lookup"><span data-stu-id="55b34-236">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="55b34-237">Джон</span><span class="sxs-lookup"><span data-stu-id="55b34-237">John</span></span>|<span data-ttu-id="55b34-238">Париж</span><span class="sxs-lookup"><span data-stu-id="55b34-238">Paris</span></span>|  
|<span data-ttu-id="55b34-239">Джейн</span><span class="sxs-lookup"><span data-stu-id="55b34-239">Jane</span></span>|<span data-ttu-id="55b34-240">Прага</span><span class="sxs-lookup"><span data-stu-id="55b34-240">Prague</span></span>|  
|<span data-ttu-id="55b34-241">Сьюзан</span><span class="sxs-lookup"><span data-stu-id="55b34-241">Susan</span></span>|<span data-ttu-id="55b34-242">Богота</span><span class="sxs-lookup"><span data-stu-id="55b34-242">Bogata</span></span>|  
  
##  <a name="example-table-and-row-size-computation"></a><a name="bkmk_ExampleComputation"></a> <span data-ttu-id="55b34-243">Пример. Вычисление размера строки и таблицы</span><span class="sxs-lookup"><span data-stu-id="55b34-243">Example: Table and Row Size Computation</span></span>  
 <span data-ttu-id="55b34-244">Для хэш-индекса фактическое число контейнеров округляется в сторону увеличения до ближайшей степени числа 2.</span><span class="sxs-lookup"><span data-stu-id="55b34-244">For hash indexes, the actual bucket count is rounded up to the nearest power of 2.</span></span> <span data-ttu-id="55b34-245">Например, если заданное число bucket_count равно 100000, то фактическое число контейнеров для индекса составляет 131072.</span><span class="sxs-lookup"><span data-stu-id="55b34-245">For example, if the specified bucket_count is 100000, the actual bucket count for the index is 131072.</span></span>  
  
 <span data-ttu-id="55b34-246">Рассмотрим таблицу Orders со следующим определением:</span><span class="sxs-lookup"><span data-stu-id="55b34-246">Consider an Orders table with the following definition:</span></span>  
  
```sql  
CREATE TABLE dbo.Orders (  
     OrderID int NOT NULL   
           PRIMARY KEY NONCLUSTERED,  
     CustomerID int NOT NULL   
           INDEX IX_CustomerID HASH WITH (BUCKET_COUNT=10000),  
     OrderDate datetime NOT NULL,  
     OrderDescription nvarchar(1000)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
```  
  
 <span data-ttu-id="55b34-247">Обратите внимание, что эта таблица содержит один хэш-индекс и некластеризованный индекс (первичный ключ).</span><span class="sxs-lookup"><span data-stu-id="55b34-247">Notice that this table has one hash index and a nonclustered index (the primary key).</span></span> <span data-ttu-id="55b34-248">Кроме того, она содержит три столбца фиксированной длины и один столбец переменной длины, при этом один из столбцов допускает значения NULL (OrderDescription).</span><span class="sxs-lookup"><span data-stu-id="55b34-248">It also has three fixed-length columns and one variable-length column, with one of the columns being NULLable (OrderDescription).</span></span> <span data-ttu-id="55b34-249">Предположим, что таблица Orders содержит 8379 строк, а средняя длина значений в столбце OrderDescription составляет 78 символов.</span><span class="sxs-lookup"><span data-stu-id="55b34-249">Let's assume the Orders table has 8379 rows, and the average length of the values in the OrderDescription column is 78 characters.</span></span>  
  
 <span data-ttu-id="55b34-250">Чтобы определить размер таблицы, сначала необходимо определить размер индексов.</span><span class="sxs-lookup"><span data-stu-id="55b34-250">To determine the table size, first determine the size of the indexes.</span></span> <span data-ttu-id="55b34-251">Для обоих индексов указан показатель bucket_count, равный 10 000.</span><span class="sxs-lookup"><span data-stu-id="55b34-251">The bucket_count for both indexes is specified as 10000.</span></span> <span data-ttu-id="55b34-252">Эта величина округляется в большую сторону до ближайшей степени числа 2: 16384.</span><span class="sxs-lookup"><span data-stu-id="55b34-252">This is rounded up to the nearest power of 2: 16384.</span></span> <span data-ttu-id="55b34-253">Поэтому общий размер индексов для таблицы Orders составляет:</span><span class="sxs-lookup"><span data-stu-id="55b34-253">Therefore, the total size of the indexes for the Orders table is:</span></span>  
  
```  
8 * 16384 = 131072 bytes  
```  
  
 <span data-ttu-id="55b34-254">Остается найти размер данных таблицы, который равен</span><span class="sxs-lookup"><span data-stu-id="55b34-254">What remains is the table data size, which is,</span></span>  
  
```  
[row size] * [row count] = [row size] * 8379  
```  
  
 <span data-ttu-id="55b34-255">(Пример таблицы содержит 8379 строк.) Теперь у нас есть:</span><span class="sxs-lookup"><span data-stu-id="55b34-255">(The example table has 8379 rows.) Now, we have:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices] = 24 + 8 * 1 = 32 bytes  
```  
  
 <span data-ttu-id="55b34-256">Теперь давайте рассчитаем [фактический размер текста строки].</span><span class="sxs-lookup"><span data-stu-id="55b34-256">Next, let's calculate [actual row body size]:</span></span>  
  
-   <span data-ttu-id="55b34-257">Столбцы поверхностных типов:</span><span class="sxs-lookup"><span data-stu-id="55b34-257">Shallow type columns:</span></span>  
  
    ```  
    SUM([size of shallow types]) = 4 [int] + 4 [int] + 8 [datetime] = 16  
    ```  
  
-   <span data-ttu-id="55b34-258">Заполнение для столбцов поверхностных типов равно 0, поскольку общий размер столбцов поверхностного типа является четным числом.</span><span class="sxs-lookup"><span data-stu-id="55b34-258">Shallow column padding is 0, as the total shallow column size is even.</span></span>  
  
-   <span data-ttu-id="55b34-259">Массив смещений для столбцов глубоких типов:</span><span class="sxs-lookup"><span data-stu-id="55b34-259">Offset array for deep type columns:</span></span>  
  
    ```  
    2 + 2 * [number of deep type columns] = 2 + 2 * 1 = 4  
    ```  
  
-   <span data-ttu-id="55b34-260">Массив значений NULL = 1</span><span class="sxs-lookup"><span data-stu-id="55b34-260">NULL array = 1</span></span>  
  
-   <span data-ttu-id="55b34-261">Заполнение массива значений NULL = 1, так как размер массива значений NULL является нечетным числом, а в таблице есть столбцы глубоких типов.</span><span class="sxs-lookup"><span data-stu-id="55b34-261">NULL array padding = 1, as the NULL array size is odd and there is a deep type column.</span></span>  
  
-   <span data-ttu-id="55b34-262">Заполнение</span><span class="sxs-lookup"><span data-stu-id="55b34-262">Padding</span></span>  
  
    -   <span data-ttu-id="55b34-263">8 — наибольшее требования выравнивания.</span><span class="sxs-lookup"><span data-stu-id="55b34-263">8 is the largest alignment requirement.</span></span>  
  
    -   <span data-ttu-id="55b34-264">Размер на данный момент равен 16 + 0 + 4 + 1 + 1 = 22.</span><span class="sxs-lookup"><span data-stu-id="55b34-264">Size so far is 16 + 0 + 4 + 1 + 1 = 22.</span></span>  
  
    -   <span data-ttu-id="55b34-265">Ближайшее число, кратное 8, — это 24.</span><span class="sxs-lookup"><span data-stu-id="55b34-265">Nearest multiple of 8 is 24.</span></span>  
  
    -   <span data-ttu-id="55b34-266">В итоге заполнение составляет 24 – 22 = 2 байта.</span><span class="sxs-lookup"><span data-stu-id="55b34-266">Total padding is 24 - 22 = 2 bytes.</span></span>  
  
-   <span data-ttu-id="55b34-267">В таблице нет столбцов глубоких типов фиксированной длины (столбцов глубоких типов фиксированной длины: 0).</span><span class="sxs-lookup"><span data-stu-id="55b34-267">There are no fixed-length deep type columns (Fixed-length deep type columns: 0.).</span></span>  
  
-   <span data-ttu-id="55b34-268">Фактический размер столбца глубокого типа составляет 2 \* 78 = 156.</span><span class="sxs-lookup"><span data-stu-id="55b34-268">The actual size of deep type column is 2 \* 78 = 156.</span></span> <span data-ttu-id="55b34-269">Единственный столбец глубокого типа OrderDescription имеет тип nvarchar.</span><span class="sxs-lookup"><span data-stu-id="55b34-269">The single deep type column OrderDescription has type nvarchar.</span></span>  
  
```  
[actual row body size] = 24 + 156 = 180 bytes  
```  
  
 <span data-ttu-id="55b34-270">Для завершения вычисления:</span><span class="sxs-lookup"><span data-stu-id="55b34-270">To complete the calculation:</span></span>  
  
```  
[row size] = 32 + 180 = 212 bytes  
[table size] = 8 * 16384 + 212 * 8379 = 131072 + 1776348 = 1907420  
```  
  
 <span data-ttu-id="55b34-271">Таким образом, общий размер, занимаемый таблицей в памяти, составляет около 2 мегабайт.</span><span class="sxs-lookup"><span data-stu-id="55b34-271">Total table size in memory is thus approximately 2 megabytes.</span></span> <span data-ttu-id="55b34-272">Это значение не учитывает потенциальные издержки при выделении памяти, а также управление версиями строк, необходимое для доступа транзакций к этой таблице.</span><span class="sxs-lookup"><span data-stu-id="55b34-272">This does not account for potential overhead incurred by memory allocation as well as any row versioning required for the transactions accessing this table.</span></span>  
  
 <span data-ttu-id="55b34-273">Фактический размер памяти, выделяемый для данной таблицы и используемый ею и ее индексами, можно получить при помощи следующего запроса:</span><span class="sxs-lookup"><span data-stu-id="55b34-273">The actual memory allocated for and used by this table and its indexes can be obtained through the following query:</span></span>  
  
```sql  
select * from sys.dm_db_xtp_table_memory_stats  
where object_id = object_id('dbo.Orders')  
```  
  
## <a name="see-also"></a><span data-ttu-id="55b34-274">См. также:</span><span class="sxs-lookup"><span data-stu-id="55b34-274">See Also</span></span>  
 [<span data-ttu-id="55b34-275">Таблицы, оптимизированные для памяти</span><span class="sxs-lookup"><span data-stu-id="55b34-275">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
