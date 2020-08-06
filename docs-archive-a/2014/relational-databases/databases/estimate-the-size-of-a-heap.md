---
title: Оценка размера кучи | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- estimating heap size
- size [SQL Server], heap
- space [SQL Server], indexes
- heaps
ms.assetid: 81fd5ec9-ce0f-4c2c-8ba0-6c483cea6c75
author: stevestein
ms.author: sstein
ms.openlocfilehash: f32432d07a9731d849ceb793daf209cfc505b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668884"
---
# <a name="estimate-the-size-of-a-heap"></a><span data-ttu-id="b8d92-102">Оценка размера кучи</span><span class="sxs-lookup"><span data-stu-id="b8d92-102">Estimate the Size of a Heap</span></span>
  <span data-ttu-id="b8d92-103">Для оценки размера пространства, требуемого для хранения данных в куче, можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="b8d92-103">You can use the following steps to estimate the amount of space that is required to store data in a heap:</span></span>  
  
1.  <span data-ttu-id="b8d92-104">Укажите количество строк в новой таблице:</span><span class="sxs-lookup"><span data-stu-id="b8d92-104">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="b8d92-105">***Num_Rows***  = число строк в таблице</span><span class="sxs-lookup"><span data-stu-id="b8d92-105">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="b8d92-106">Укажите количество столбцов с фиксированной и изменяемой длиной, а также рассчитайте необходимый размер места для их хранения.</span><span class="sxs-lookup"><span data-stu-id="b8d92-106">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="b8d92-107">Вычислите размер, занимаемый каждой из этих групп столбцов в строке данных.</span><span class="sxs-lookup"><span data-stu-id="b8d92-107">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="b8d92-108">Размер столбца зависит от типа данных и длины.</span><span class="sxs-lookup"><span data-stu-id="b8d92-108">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="b8d92-109">***Num_Cols***  = общее количество столбцов (фиксированной и переменной ширины)</span><span class="sxs-lookup"><span data-stu-id="b8d92-109">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="b8d92-110">***Fixed_Data_Size***  = общий размер в байтах всех ключевых столбцов фиксированной длины</span><span class="sxs-lookup"><span data-stu-id="b8d92-110">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="b8d92-111">***Num_Variable_Cols***  = количество включенных столбцов переменной длины</span><span class="sxs-lookup"><span data-stu-id="b8d92-111">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="b8d92-112">***Max_Var_Size*** = максимальный общий размер в байтах всех столбцов переменной длины</span><span class="sxs-lookup"><span data-stu-id="b8d92-112">***Max_Var_Size***  = maximum total byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="b8d92-113">Часть строки, называемая битовой картой NULL, зарезервирована для управления свойством столбца принимать значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b8d92-113">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="b8d92-114">Вычислите ее размер.</span><span class="sxs-lookup"><span data-stu-id="b8d92-114">Calculate its size:</span></span>  
  
     <span data-ttu-id="b8d92-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="b8d92-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="b8d92-116">Следует использовать только целую часть этого выражения и</span><span class="sxs-lookup"><span data-stu-id="b8d92-116">Only the integer part of this expression should be used.</span></span> <span data-ttu-id="b8d92-117">Остаток должен быть отброшен.</span><span class="sxs-lookup"><span data-stu-id="b8d92-117">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="b8d92-118">Расчет размера данных с переменной длиной:</span><span class="sxs-lookup"><span data-stu-id="b8d92-118">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="b8d92-119">Если таблица содержит столбцы с переменной длиной, определите, сколько пространства потребуется для хранения столбцов в строке:</span><span class="sxs-lookup"><span data-stu-id="b8d92-119">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="b8d92-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="b8d92-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="b8d92-121">Добавленные к значению ***Max_Var_Size*** байты необходимы для отслеживания каждого столбца переменной длины.</span><span class="sxs-lookup"><span data-stu-id="b8d92-121">The bytes added to ***Max_Var_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="b8d92-122">Эта формула исходит из предположения, что все столбцы переменной длины заполнены на 100 %.</span><span class="sxs-lookup"><span data-stu-id="b8d92-122">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="b8d92-123">Если предполагается, что будет использовано меньше места для хранения столбца изменяемой длины, можно изменить значение ***Max_Var_Size*** в процентах от общей изменяемой длины для более точного подсчета общего размера таблицы.</span><span class="sxs-lookup"><span data-stu-id="b8d92-123">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8d92-124">Можно сочетать столбцы `varchar`, `nvarchar`, `varbinary` или `sql_variant`, в результате чего общая ширина определенной таблицы превысит 8060 байт.</span><span class="sxs-lookup"><span data-stu-id="b8d92-124">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="b8d92-125">Длина каждого из этих столбцов по-прежнему должна находиться в пределах 8 000 байт для `varchar` `nvarchar,``varbinary` столбца, или `sql_variant` .</span><span class="sxs-lookup"><span data-stu-id="b8d92-125">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `nvarchar,``varbinary`, or `sql_variant` column.</span></span> <span data-ttu-id="b8d92-126">Тем не менее их общая ширина в таблице может превышать предел в 8 060 байт.</span><span class="sxs-lookup"><span data-stu-id="b8d92-126">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="b8d92-127">Если в таблице нет столбцов переменной ширины, присвойте параметру ***Variable_Data_Size*** значение 0.</span><span class="sxs-lookup"><span data-stu-id="b8d92-127">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="b8d92-128">Вычислите общий размер строк:</span><span class="sxs-lookup"><span data-stu-id="b8d92-128">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="b8d92-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="b8d92-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="b8d92-130">Значение 4 в формуле — это служебные данные заголовка строки данных.</span><span class="sxs-lookup"><span data-stu-id="b8d92-130">The value 4 in the formula is the row header overhead of the data row.</span></span>  
  
6.  <span data-ttu-id="b8d92-131">Расчет количества строк на странице (8 096 свободных байт на страницу):</span><span class="sxs-lookup"><span data-stu-id="b8d92-131">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="b8d92-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="b8d92-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="b8d92-133">Так как строки не могут разрываться на разные страницы, общее количество строк на страницу необходимо округлить до меньшего целого значения целой строки.</span><span class="sxs-lookup"><span data-stu-id="b8d92-133">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="b8d92-134">Значение 2 в формуле соответствует записи строки в массиве областей памяти страницы.</span><span class="sxs-lookup"><span data-stu-id="b8d92-134">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
7.  <span data-ttu-id="b8d92-135">Вычислите количество страниц, необходимое для хранения всех строк:</span><span class="sxs-lookup"><span data-stu-id="b8d92-135">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="b8d92-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span><span class="sxs-lookup"><span data-stu-id="b8d92-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span></span>  
  
     <span data-ttu-id="b8d92-137">Вычисленное количество страниц должно быть округлено в большую сторону до ближайшей целой страницы.</span><span class="sxs-lookup"><span data-stu-id="b8d92-137">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
8.  <span data-ttu-id="b8d92-138">Вычислите размер пространства, требуемого для хранения данных в куче (всего 8192 на страницу):</span><span class="sxs-lookup"><span data-stu-id="b8d92-138">Calculate the amount of space that is required to store the data in the heap (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="b8d92-139">Размер кучи (в байтах) = 8192 x ***Num_Pages***</span><span class="sxs-lookup"><span data-stu-id="b8d92-139">Heap size (bytes) = 8192 x ***Num_Pages***</span></span>  
  
 <span data-ttu-id="b8d92-140">Этот расчет не учитывает следующие факторы.</span><span class="sxs-lookup"><span data-stu-id="b8d92-140">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="b8d92-141">Секционирование</span><span class="sxs-lookup"><span data-stu-id="b8d92-141">Partitioning</span></span>  
  
     <span data-ttu-id="b8d92-142">Размер служебных данных секционирования минимален, но его сложно рассчитать.</span><span class="sxs-lookup"><span data-stu-id="b8d92-142">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="b8d92-143">Он не столь важен, чтобы включать в расчеты.</span><span class="sxs-lookup"><span data-stu-id="b8d92-143">It is not important to include.</span></span>  
  
-   <span data-ttu-id="b8d92-144">Страницы размещения</span><span class="sxs-lookup"><span data-stu-id="b8d92-144">Allocation pages</span></span>  
  
     <span data-ttu-id="b8d92-145">Предусмотрена по меньшей мере одна IAM-страница, используемая для отслеживания страниц, выделенных куче, но размер служебных данных минимален, и алгоритма точного детерминированного вычисления количества используемых IAM-страниц не существует.</span><span class="sxs-lookup"><span data-stu-id="b8d92-145">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="b8d92-146">Значения LOB</span><span class="sxs-lookup"><span data-stu-id="b8d92-146">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="b8d92-147">Алгоритм для определения того, какой объем пространства будет использоваться для хранения типов данных LOB,,,, `varchar(max)` `varbinary(max)` `nvarchar(max)` `text` **нтекстксмл**, и `image` является сложным.</span><span class="sxs-lookup"><span data-stu-id="b8d92-147">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, **ntextxml**, and `image` values is complex.</span></span> <span data-ttu-id="b8d92-148">Достаточно просто прибавить ожидаемую среднюю величину значений LOB к общему размеру кучи.</span><span class="sxs-lookup"><span data-stu-id="b8d92-148">It is sufficient to just add the average size of the LOB values that are expected and add that to the total heap size.</span></span>  
  
-   <span data-ttu-id="b8d92-149">Сжатие</span><span class="sxs-lookup"><span data-stu-id="b8d92-149">Compression</span></span>  
  
     <span data-ttu-id="b8d92-150">Размер сжатой кучи нельзя вычислить заранее.</span><span class="sxs-lookup"><span data-stu-id="b8d92-150">You cannot pre-calculate the size of a compressed heap.</span></span>  
  
-   <span data-ttu-id="b8d92-151">Разреженные столбцы</span><span class="sxs-lookup"><span data-stu-id="b8d92-151">Sparse columns</span></span>  
  
     <span data-ttu-id="b8d92-152">Сведения о требованиях разреженных столбцов к месту на диске см. в разделе [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="b8d92-152">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d92-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="b8d92-153">See Also</span></span>  
 <span data-ttu-id="b8d92-154">[Кучи (таблицы без кластеризованных индексов)](../indexes/heaps-tables-without-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="b8d92-154">[Heaps &#40;Tables without Clustered Indexes&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span></span>  
 <span data-ttu-id="b8d92-155">[Описания кластеризованных и некластеризованных индексов](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="b8d92-155">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="b8d92-156">[Создание кластеризованных индексов](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="b8d92-156">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="b8d92-157">[Создание некластеризованных индексов](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="b8d92-157">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="b8d92-158">[Оценка размера таблицы](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="b8d92-158">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="b8d92-159">[Оценка размера кластеризованного индекса](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="b8d92-159">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="b8d92-160">[Оценка размера некластеризованного индекса](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="b8d92-160">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 [<span data-ttu-id="b8d92-161">Оценка размера базы данных</span><span class="sxs-lookup"><span data-stu-id="b8d92-161">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
