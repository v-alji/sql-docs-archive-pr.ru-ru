---
title: Оценка размера кластеризованного индекса | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- disk space [SQL Server], indexes
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- space [SQL Server], indexes
- clustered indexes, table size
- nonclustered indexes [SQL Server], table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: 2b5137f8-98ad-46b5-9aae-4c980259bf8d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d224c5ae55cc5ec7690ca0962cbc2130bac22e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751088"
---
# <a name="estimate-the-size-of-a-clustered-index"></a><span data-ttu-id="e0add-102">Оценка размера кластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="e0add-102">Estimate the Size of a Clustered Index</span></span>
  <span data-ttu-id="e0add-103">Для оценки места, необходимого для хранения данных в кластеризованном индексе, можно использовать следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="e0add-103">You can use the following steps to estimate the amount of space that is required to store data in a clustered index:</span></span>  
  
1.  <span data-ttu-id="e0add-104">Рассчитайте пространство, используемое для хранения данных на конечном уровне кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="e0add-104">Calculate the space used to store data in the leaf level of the clustered index.</span></span>  
  
2.  <span data-ttu-id="e0add-105">Рассчитайте пространство, используемое для хранения сведений об индексе для кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="e0add-105">Calculate the space used to store index information for the clustered index.</span></span>  
  
3.  <span data-ttu-id="e0add-106">Сложите полученные значения.</span><span class="sxs-lookup"><span data-stu-id="e0add-106">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-the-space-used-to-store-data-in-the-leaf-level"></a><span data-ttu-id="e0add-107">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="e0add-107">Step 1.</span></span> <span data-ttu-id="e0add-108">Расчет пространства, используемого для хранения данных на конечном уровне</span><span class="sxs-lookup"><span data-stu-id="e0add-108">Calculate the Space Used to Store Data in the Leaf Level</span></span>  
  
1.  <span data-ttu-id="e0add-109">Укажите количество строк в новой таблице:</span><span class="sxs-lookup"><span data-stu-id="e0add-109">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="e0add-110">***Num_Rows***  = число строк в таблице</span><span class="sxs-lookup"><span data-stu-id="e0add-110">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="e0add-111">Укажите количество столбцов с фиксированной и изменяемой длиной, а также рассчитайте необходимый размер места для их хранения.</span><span class="sxs-lookup"><span data-stu-id="e0add-111">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="e0add-112">Вычислите размер, занимаемый каждой из этих групп столбцов в строке данных.</span><span class="sxs-lookup"><span data-stu-id="e0add-112">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="e0add-113">Размер столбца зависит от типа данных и длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-113">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="e0add-114">***Num_Cols***  = общее количество столбцов (фиксированной и переменной ширины)</span><span class="sxs-lookup"><span data-stu-id="e0add-114">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="e0add-115">***Fixed_Data_Size***  = общий размер в байтах всех ключевых столбцов фиксированной длины</span><span class="sxs-lookup"><span data-stu-id="e0add-115">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="e0add-116">***Num_Variable_Cols***  = количество включенных столбцов переменной длины</span><span class="sxs-lookup"><span data-stu-id="e0add-116">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="e0add-117">***Max_Var_Size***  = максимальный размер в байтах всех столбцов переменной длины</span><span class="sxs-lookup"><span data-stu-id="e0add-117">***Max_Var_Size***  = maximum byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="e0add-118">Если кластеризованный индекс не является уникальным, учитывается столбец *uniquifier* :</span><span class="sxs-lookup"><span data-stu-id="e0add-118">If the clustered index is nonunique, account for the *uniqueifier* column:</span></span>  
  
     <span data-ttu-id="e0add-119">Столбец uniquifier может принимать значение NULL и имеет переменную длину.</span><span class="sxs-lookup"><span data-stu-id="e0add-119">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="e0add-120">Он будет иметь значение, отличное от NULL, и размер 4 байта для строк, имеющих неуникальные значения ключа.</span><span class="sxs-lookup"><span data-stu-id="e0add-120">It will be nonnull and 4 bytes in size in rows that have nonunique key values.</span></span> <span data-ttu-id="e0add-121">Это значение является частью ключа индекса и требует уникальности значения ключа во всех строках.</span><span class="sxs-lookup"><span data-stu-id="e0add-121">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="e0add-122">***Num_Cols***  = ***Num_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e0add-122">***Num_Cols***  = ***Num_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e0add-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e0add-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e0add-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="e0add-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span></span>  
  
     <span data-ttu-id="e0add-125">Эти изменения предполагают, что все значения станут неуникальными.</span><span class="sxs-lookup"><span data-stu-id="e0add-125">These modifications assume that all values will be nonunique.</span></span>  
  
4.  <span data-ttu-id="e0add-126">Часть строки, называемая битовой картой NULL, зарезервирована для управления свойством столбца принимать значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e0add-126">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="e0add-127">Вычислите ее размер.</span><span class="sxs-lookup"><span data-stu-id="e0add-127">Calculate its size:</span></span>  
  
     <span data-ttu-id="e0add-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="e0add-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="e0add-129">Используется только целая часть предыдущего выражения, остальная часть отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="e0add-129">Only the integer part of the previous expression should be used; discard any remainder.</span></span>  
  
5.  <span data-ttu-id="e0add-130">Расчет размера данных с переменной длиной:</span><span class="sxs-lookup"><span data-stu-id="e0add-130">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="e0add-131">Если таблица содержит столбцы с переменной длиной, определите, сколько пространства потребуется для хранения столбцов в строке:</span><span class="sxs-lookup"><span data-stu-id="e0add-131">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="e0add-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="e0add-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="e0add-133">Байты, добавляемые к ***Max_Var_Size*** , нужны для отслеживания каждого столбца переменных.</span><span class="sxs-lookup"><span data-stu-id="e0add-133">The bytes added to ***Max_Var_Size*** are for tracking each variable column.</span></span> <span data-ttu-id="e0add-134">Эта формула исходит из предположения, что все столбцы переменной длины заполнены на 100 %.</span><span class="sxs-lookup"><span data-stu-id="e0add-134">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="e0add-135">Если предполагается, что будет использовано меньше места для хранения столбца изменяемой длины, можно изменить значение ***Max_Var_Size*** в процентах от общей изменяемой длины для более точного подсчета общего размера таблицы.</span><span class="sxs-lookup"><span data-stu-id="e0add-135">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0add-136">Можно сочетать столбцы `varchar`, `nvarchar`, `varbinary` или `sql_variant`, в результате чего общая ширина определенной таблицы превысит 8060 байт.</span><span class="sxs-lookup"><span data-stu-id="e0add-136">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="e0add-137">Длина каждого из этих столбцов должна быть в пределах 8 000 байт для столбцов типа `varchar`, `varbinary` или `sql_variant` и 4 000 байт для столбцов типа `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="e0add-137">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="e0add-138">Тем не менее их общая ширина в таблице может превышать предел в 8 060 байт.</span><span class="sxs-lookup"><span data-stu-id="e0add-138">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="e0add-139">Если в таблице нет столбцов переменной ширины, присвойте параметру ***Variable_Data_Size*** значение 0.</span><span class="sxs-lookup"><span data-stu-id="e0add-139">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="e0add-140">Вычислите общий размер строк:</span><span class="sxs-lookup"><span data-stu-id="e0add-140">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="e0add-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="e0add-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="e0add-142">Значение 4 является размером заголовка строки.</span><span class="sxs-lookup"><span data-stu-id="e0add-142">The value 4 is the row header overhead of a data row.</span></span>  
  
7.  <span data-ttu-id="e0add-143">Расчет количества строк на странице (8 096 свободных байт на страницу):</span><span class="sxs-lookup"><span data-stu-id="e0add-143">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="e0add-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e0add-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e0add-145">Так как строки не могут разрываться на разные страницы, общее количество строк на страницу необходимо округлить до меньшего целого значения целой строки.</span><span class="sxs-lookup"><span data-stu-id="e0add-145">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e0add-146">Значение 2 в формуле соответствует записи строки в массиве областей памяти страницы.</span><span class="sxs-lookup"><span data-stu-id="e0add-146">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
8.  <span data-ttu-id="e0add-147">Рассчет количества зарезервированных пустых строк на странице на основании указанного [коэффициента заполнения](../indexes/specify-fill-factor-for-an-index.md) :</span><span class="sxs-lookup"><span data-stu-id="e0add-147">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="e0add-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e0add-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e0add-149">Коэффициент заполнения, используемый в расчете, должен быть целым значением, а не процентным соотношением.</span><span class="sxs-lookup"><span data-stu-id="e0add-149">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="e0add-150">Так как строки не могут разрываться на разные страницы, общее количество строк на страницу необходимо округлить до меньшего целого значения целой строки.</span><span class="sxs-lookup"><span data-stu-id="e0add-150">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e0add-151">При увеличении коэффициента заполнения на каждой странице будет сохранено больше данных и, соответственно, потребуется меньше страниц.</span><span class="sxs-lookup"><span data-stu-id="e0add-151">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="e0add-152">Значение 2 в формуле соответствует записи строки в массиве областей памяти страницы.</span><span class="sxs-lookup"><span data-stu-id="e0add-152">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
9. <span data-ttu-id="e0add-153">Вычислите количество страниц, необходимое для хранения всех строк:</span><span class="sxs-lookup"><span data-stu-id="e0add-153">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="e0add-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="e0add-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="e0add-155">Вычисленное количество страниц должно быть округлено в большую сторону до ближайшей целой страницы.</span><span class="sxs-lookup"><span data-stu-id="e0add-155">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
10. <span data-ttu-id="e0add-156">Расчет количества места, необходимого для хранения данных на конечном уровне (всего 8 192 байт на страницу):</span><span class="sxs-lookup"><span data-stu-id="e0add-156">Calculate the amount of space that is required to store the data in the leaf level (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="e0add-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="e0add-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information"></a><span data-ttu-id="e0add-158">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="e0add-158">Step 2.</span></span> <span data-ttu-id="e0add-159">Расчет пространства, используемого для хранения данных индекса</span><span class="sxs-lookup"><span data-stu-id="e0add-159">Calculate the Space Used to Store Index Information</span></span>  
 <span data-ttu-id="e0add-160">Для оценки места, необходимого для хранения верхних уровней индекса, можно использовать следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="e0add-160">You can use the following steps to estimate the amount of space that is required to store the upper levels of the index:</span></span>  
  
1.  <span data-ttu-id="e0add-161">Укажите количество столбцов переменной и фиксированной длины в ключе индекса и рассчитайте объем необходимого места для их хранения:</span><span class="sxs-lookup"><span data-stu-id="e0add-161">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="e0add-162">Ключевые столбцы индекса могут включать в себя столбцы постоянной и переменной длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-162">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="e0add-163">Чтобы вычислить размер строки индекса на внутреннем уровне, нужно рассчитать, сколько места занимает в строке индекса каждая из этих групп столбцов.</span><span class="sxs-lookup"><span data-stu-id="e0add-163">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="e0add-164">Размер столбца зависит от типа данных и длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-164">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="e0add-165">***Num_Key_Cols***  возвращает общее количество ключевых столбцов (фиксированной и переменной ширины).</span><span class="sxs-lookup"><span data-stu-id="e0add-165">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="e0add-166">***Fixed_Key_Size***  возвращает общий размер в байтах всех ключевых столбцов фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-166">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="e0add-167">***Num_Variable_Key_Cols***  возвращает количество ключевых столбцов переменной длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-167">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="e0add-168">***Max_Var_Key_Size***  возвращает максимальный размер в байтах ключевых столбцов переменной длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-168">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
2.  <span data-ttu-id="e0add-169">Если индекс является неуникальным, необходимо учитывать любой столбец uniquifier:</span><span class="sxs-lookup"><span data-stu-id="e0add-169">Account for any uniqueifier needed if the index is nonunique:</span></span>  
  
     <span data-ttu-id="e0add-170">Столбец uniquifier может принимать значение NULL и имеет переменную длину.</span><span class="sxs-lookup"><span data-stu-id="e0add-170">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="e0add-171">Он будет иметь значение, отличное от NULL, и размер 4 байта для строк, имеющих неуникальные значения ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="e0add-171">It will be nonnull and 4 bytes in size in rows that have nonunique index key values.</span></span> <span data-ttu-id="e0add-172">Это значение является частью ключа индекса и требует уникальности значения ключа во всех строках.</span><span class="sxs-lookup"><span data-stu-id="e0add-172">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="e0add-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e0add-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e0add-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e0add-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e0add-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="e0add-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span></span>  
  
     <span data-ttu-id="e0add-176">Эти изменения предполагают, что все значения станут неуникальными.</span><span class="sxs-lookup"><span data-stu-id="e0add-176">These modifications assume that all values will be nonunique.</span></span>  
  
3.  <span data-ttu-id="e0add-177">Рассчет размера битовой карты NULL:</span><span class="sxs-lookup"><span data-stu-id="e0add-177">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="e0add-178">Если в ключе индекса существуют столбцы, допускающие значение NULL, то часть индексной строки резервируется для битовой карты NULL.</span><span class="sxs-lookup"><span data-stu-id="e0add-178">If there are nullable columns in the index key, part of the index row is reserved for the null bitmap.</span></span> <span data-ttu-id="e0add-179">Вычислите ее размер.</span><span class="sxs-lookup"><span data-stu-id="e0add-179">Calculate its size:</span></span>  
  
     <span data-ttu-id="e0add-180">***Index_Null_Bitmap***  = 2 + ((количество столбцов в строке индекса + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="e0add-180">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="e0add-181">Следует использовать только целую часть предшествующего выражения.</span><span class="sxs-lookup"><span data-stu-id="e0add-181">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="e0add-182">Остаток должен быть отброшен.</span><span class="sxs-lookup"><span data-stu-id="e0add-182">Discard any remainder.</span></span>  
  
     <span data-ttu-id="e0add-183">Если нет ключевых столбцов, допускающих значения NULL, установите параметр ***Index_Null_Bitmap*** на 0.</span><span class="sxs-lookup"><span data-stu-id="e0add-183">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
4.  <span data-ttu-id="e0add-184">Расчет размера данных с переменной длиной:</span><span class="sxs-lookup"><span data-stu-id="e0add-184">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="e0add-185">Если индекс содержит столбцы с переменной длиной, определим, сколько пространства потребуется для хранения этих столбцов в строке:</span><span class="sxs-lookup"><span data-stu-id="e0add-185">If there are variable-length columns in the index, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="e0add-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="e0add-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="e0add-187">Байты, добавляемые к ***Max_Var_Key_Size*** , нужны для отслеживания каждого столбца переменной длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-187">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="e0add-188">Эта формула исходит из предположения, что все столбцы переменной длины заполнены на 100 %.</span><span class="sxs-lookup"><span data-stu-id="e0add-188">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="e0add-189">Если предполагается, что для хранения столбца переменной длины будет использовано меньше места, то для более точного подсчета общего размера таблицы можно задать значение ***Max_Var_Key_Size*** как процент от максимально возможной длины.</span><span class="sxs-lookup"><span data-stu-id="e0add-189">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="e0add-190">Если нет столбцов переменной ширины, установите значение ***Variable_Key_Size*** равным 0.</span><span class="sxs-lookup"><span data-stu-id="e0add-190">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="e0add-191">Расчет размера индексной строки:</span><span class="sxs-lookup"><span data-stu-id="e0add-191">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="e0add-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (для служебных данных строки заголовка индекса) + 6 (для указателя на идентификатор дочерней страницы)</span><span class="sxs-lookup"><span data-stu-id="e0add-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="e0add-193">Расчет количества индексных строк на страницу (8 096 свободных байт на страницу):</span><span class="sxs-lookup"><span data-stu-id="e0add-193">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="e0add-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e0add-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e0add-195">Так как строка индекса не может быть разорвана на две страницы, общее количество строк индекса на странице необходимо округлить в меньшую сторону до ближайшего целого значения.</span><span class="sxs-lookup"><span data-stu-id="e0add-195">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e0add-196">Значение 2 в формуле соответствует записи строки в массиве слота страницы.</span><span class="sxs-lookup"><span data-stu-id="e0add-196">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="e0add-197">Расчет количества уровней в индексе.</span><span class="sxs-lookup"><span data-stu-id="e0add-197">Calculate the number of levels in the index:</span></span>  
  
     <span data-ttu-id="e0add-198">***Не leaf_Levels*** = 1 + Index_Rows_Per_Page журнала (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="e0add-198">***Non-leaf_Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="e0add-199">Данное значение округляется в большую сторону до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="e0add-199">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="e0add-200">Это значение не учитывает конечный уровень кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="e0add-200">This value does not include the leaf level of the clustered index.</span></span>  
  
8.  <span data-ttu-id="e0add-201">Вычислите количество неконечных страниц индекса:</span><span class="sxs-lookup"><span data-stu-id="e0add-201">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="e0add-202">***Num_Index_Pages =*** уровень ∑ ***(Num_Leaf_Pages/(***<sup>уровень</sup>Index_Rows_Per_Page ***))***</span><span class="sxs-lookup"><span data-stu-id="e0add-202">***Num_Index_Pages =*** ∑Level ***(Num_Leaf_Pages / (Index_Rows_Per_Page***<sup>Level</sup>***))***</span></span>  
  
     <span data-ttu-id="e0add-203">где 1 <= Уровень <= ***Non-leaf_Levels***</span><span class="sxs-lookup"><span data-stu-id="e0add-203">where 1 <= Level <= ***Non-leaf_Levels***</span></span>  
  
     <span data-ttu-id="e0add-204">Округлите каждое слагаемое в большую сторону до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="e0add-204">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="e0add-205">Рассмотрим в качестве простого примера индекс, где ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="e0add-205">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="e0add-206">Первый уровень индекса над конечным уровнем содержит 1000 строк индекса, что составляет одну строку индекса на конечную страницу, а на одну страницу помещается 25 строк индекса.</span><span class="sxs-lookup"><span data-stu-id="e0add-206">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="e0add-207">Это означает, что для хранения этих 1000 строк индекса требуется 40 страниц.</span><span class="sxs-lookup"><span data-stu-id="e0add-207">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="e0add-208">Следующий уровень индекса должен хранить 40 строк.</span><span class="sxs-lookup"><span data-stu-id="e0add-208">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="e0add-209">Это означает, что ему необходимо 2 страниц.</span><span class="sxs-lookup"><span data-stu-id="e0add-209">This means it requires 2 pages.</span></span> <span data-ttu-id="e0add-210">Последний уровень индекса должен хранить 2 строки.</span><span class="sxs-lookup"><span data-stu-id="e0add-210">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="e0add-211">Это означает, что ему необходима 1 страница.</span><span class="sxs-lookup"><span data-stu-id="e0add-211">This means it requires 1 page.</span></span> <span data-ttu-id="e0add-212">Это дает 43 неконечных страницы индекса.</span><span class="sxs-lookup"><span data-stu-id="e0add-212">This gives 43 non-leaf index pages.</span></span> <span data-ttu-id="e0add-213">Использование этих значений в предыдущих формулах приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="e0add-213">When these numbers are used in the previous formulas, the outcome is as follows:</span></span>  
  
     <span data-ttu-id="e0add-214">***Не leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="e0add-214">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="e0add-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, то есть количество страниц, описываемых в примере.</span><span class="sxs-lookup"><span data-stu-id="e0add-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
9. <span data-ttu-id="e0add-216">Расчет размера индекса (всего 8 192 байт на страницу).</span><span class="sxs-lookup"><span data-stu-id="e0add-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="e0add-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="e0add-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-3-total-the-calculated-values"></a><span data-ttu-id="e0add-218">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="e0add-218">Step 3.</span></span> <span data-ttu-id="e0add-219">Сложение полученных значений</span><span class="sxs-lookup"><span data-stu-id="e0add-219">Total the Calculated Values</span></span>  
 <span data-ttu-id="e0add-220">Необходимо сложить результаты, полученные на двух предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="e0add-220">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="e0add-221">Размер кластеризованного индекса (в байтах) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="e0add-221">Clustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="e0add-222">Этот расчет не учитывает следующие факторы.</span><span class="sxs-lookup"><span data-stu-id="e0add-222">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="e0add-223">Секционирование</span><span class="sxs-lookup"><span data-stu-id="e0add-223">Partitioning</span></span>  
  
     <span data-ttu-id="e0add-224">Размер служебных данных секционирования минимален, но его сложно рассчитать.</span><span class="sxs-lookup"><span data-stu-id="e0add-224">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="e0add-225">Он не столь важен, чтобы включать в расчеты.</span><span class="sxs-lookup"><span data-stu-id="e0add-225">It is not important to include.</span></span>  
  
-   <span data-ttu-id="e0add-226">Страницы размещения</span><span class="sxs-lookup"><span data-stu-id="e0add-226">Allocation pages</span></span>  
  
     <span data-ttu-id="e0add-227">Предусмотрена по меньшей мере одна IAM-страница, используемая для отслеживания страниц, выделенных куче, но размер служебных данных минимален, и алгоритма точного детерминированного вычисления количества используемых IAM-страниц не существует.</span><span class="sxs-lookup"><span data-stu-id="e0add-227">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="e0add-228">Значения LOB</span><span class="sxs-lookup"><span data-stu-id="e0add-228">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="e0add-229">Алгоритм точного определения места, используемого для хранения значений данных типа LOB `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` и `image` сложен.</span><span class="sxs-lookup"><span data-stu-id="e0add-229">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="e0add-230">Достаточно только добавить средний размер ожидаемого значения LOB, умножить на ***Число_строк***и добавить полученное значение к общему размеру кластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="e0add-230">It is sufficient to just add the average size of the LOB values that are expected, multiply by ***Num_Rows***, and add that to the total clustered index size.</span></span>  
  
-   <span data-ttu-id="e0add-231">Сжатие</span><span class="sxs-lookup"><span data-stu-id="e0add-231">Compression</span></span>  
  
     <span data-ttu-id="e0add-232">Размер сжатого индекса нельзя вычислить заранее.</span><span class="sxs-lookup"><span data-stu-id="e0add-232">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="e0add-233">Разреженные столбцы</span><span class="sxs-lookup"><span data-stu-id="e0add-233">Sparse columns</span></span>  
  
     <span data-ttu-id="e0add-234">Сведения о требованиях разреженных столбцов к месту на диске см. в разделе [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e0add-234">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0add-235">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0add-235">See Also</span></span>  
 <span data-ttu-id="e0add-236">[Описания кластеризованных и некластеризованных индексов](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="e0add-236">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="e0add-237">[Оценка размера таблицы](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="e0add-237">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="e0add-238">[Создание кластеризованных индексов](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e0add-238">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="e0add-239">[Создание некластеризованных индексов](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e0add-239">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="e0add-240">[Оценка размера некластеризованного индекса](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="e0add-240">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 <span data-ttu-id="e0add-241">[Оценка размера кучи](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="e0add-241">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="e0add-242">Оценка размера базы данных</span><span class="sxs-lookup"><span data-stu-id="e0add-242">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
