---
title: Оценка размера некластеризованного индекса | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: c183b0e4-ef4c-4bfc-8575-5ac219c25b0a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 097c0e5568ba17b12f83d09e347eb3bf8b0bd7da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736377"
---
# <a name="estimate-the-size-of-a-nonclustered-index"></a><span data-ttu-id="9972e-102">Оценка размера некластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="9972e-102">Estimate the Size of a Nonclustered Index</span></span>
  <span data-ttu-id="9972e-103">Чтобы оценить объем пространства, необходимого для хранения некластеризованного индекса, можно выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="9972e-103">Follow these steps to estimate the amount of space that is required to store a nonclustered index:</span></span>  
  
1.  <span data-ttu-id="9972e-104">Вычислить переменные, используемые на шагах 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="9972e-104">Calculate variables for use in steps 2 and 3.</span></span>  
  
2.  <span data-ttu-id="9972e-105">Рассчитать пространство, используемое для хранения данных на конечном уровне некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-105">Calculate the space used to store index information in the leaf level of the nonclustered index.</span></span>  
  
3.  <span data-ttu-id="9972e-106">Рассчитать пространство, используемое для хранения данных индекса на неконечных уровнях некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-106">Calculate the space used to store index information in the non-leaf levels of the nonclustered index.</span></span>  
  
4.  <span data-ttu-id="9972e-107">Сложите полученные значения.</span><span class="sxs-lookup"><span data-stu-id="9972e-107">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-variables-for-use-in-steps-2-and-3"></a><span data-ttu-id="9972e-108">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="9972e-108">Step 1.</span></span> <span data-ttu-id="9972e-109">Вычисление переменных, используемых на шагах 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="9972e-109">Calculate Variables for Use in Steps 2 and 3</span></span>  
 <span data-ttu-id="9972e-110">Можно использовать следующие шаги, чтобы вычислить переменные, используемые для оценки объема пространства, необходимого для хранения верхних уровней индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-110">You can use the following steps to calculate variables that are used to estimate the amount of space that is required to store the upper levels of the index.</span></span>  
  
1.  <span data-ttu-id="9972e-111">Укажите количество строк в новой таблице:</span><span class="sxs-lookup"><span data-stu-id="9972e-111">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="9972e-112">***Num_Rows***  = число строк в таблице</span><span class="sxs-lookup"><span data-stu-id="9972e-112">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="9972e-113">Укажите количество столбцов переменной и фиксированной длины в ключе индекса и рассчитайте объем необходимого места для их хранения:</span><span class="sxs-lookup"><span data-stu-id="9972e-113">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="9972e-114">Ключевые столбцы индекса могут включать в себя столбцы постоянной и переменной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-114">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="9972e-115">Чтобы вычислить размер строки индекса на внутреннем уровне, нужно рассчитать, сколько места занимает в строке индекса каждая из этих групп столбцов.</span><span class="sxs-lookup"><span data-stu-id="9972e-115">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="9972e-116">Размер столбца зависит от типа данных и длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-116">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="9972e-117">***Num_Key_Cols***  возвращает общее количество ключевых столбцов (фиксированной и переменной ширины).</span><span class="sxs-lookup"><span data-stu-id="9972e-117">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="9972e-118">***Fixed_Key_Size***  возвращает общий размер в байтах всех ключевых столбцов фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-118">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="9972e-119">***Num_Variable_Key_Cols***  возвращает количество ключевых столбцов переменной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-119">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="9972e-120">***Max_Var_Key_Size***  возвращает максимальный размер в байтах ключевых столбцов переменной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-120">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
3.  <span data-ttu-id="9972e-121">Учтите место для указателя на строку данных, который необходим, если индекс не является уникальным.</span><span class="sxs-lookup"><span data-stu-id="9972e-121">Account for the data row locator that is required if the index is nonunique:</span></span>  
  
     <span data-ttu-id="9972e-122">Если некластеризованный индекс не является уникальным, то указатель на строку данных будет объединен с ключом некластеризованного индекса, чтобы получить уникальное ключевое значение для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="9972e-122">If the nonclustered index is nonunique, the data row locator is combined with the nonclustered index key to produce a unique key value for every row.</span></span>  
  
     <span data-ttu-id="9972e-123">Если некластеризованный индекс является индексом для кучи, указателем на строку данных служит RID кучи.</span><span class="sxs-lookup"><span data-stu-id="9972e-123">If the nonclustered index is over a heap, the data row locator is the heap RID.</span></span> <span data-ttu-id="9972e-124">Его размер составляет 8 байт.</span><span class="sxs-lookup"><span data-stu-id="9972e-124">This is a size of 8 bytes.</span></span>  
  
     <span data-ttu-id="9972e-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="9972e-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="9972e-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="9972e-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="9972e-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="9972e-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span></span>  
  
     <span data-ttu-id="9972e-128">Если некластеризованный индекс строится поверх кластеризованного, указателем строки данных является ключ кластеризации.</span><span class="sxs-lookup"><span data-stu-id="9972e-128">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="9972e-129">Столбцы, которые должны быть объединены с ключом некластеризованного индекса — это те столбцы в ключе кластеризации, которые еще не присутствуют в наборе ключевых столбцов некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-129">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="9972e-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + количество ключевых столбцов кластеризации, не вошедших в набор ключевых столбцов некластеризованного индекса (+ 1, если кластеризованный индекс неуникален)</span><span class="sxs-lookup"><span data-stu-id="9972e-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="9972e-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + общий размер в байтах ключевых столбцов кластеризации фиксированной длины, не вошедших в набор ключевых столбцов некластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="9972e-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="9972e-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + число ключевых столбцов кластеризации переменной длины, не вошедших в набор ключевых столбцов некластеризованного индекса (+ 1, если кластеризованный индекс неуникален)</span><span class="sxs-lookup"><span data-stu-id="9972e-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="9972e-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + максимальный размер в байтах ключевых столбцов кластеризации переменной длины, не вошедших в набор ключевых столбцов некластеризованного индекса (+ 4, если кластеризованный индекс неуникален)</span><span class="sxs-lookup"><span data-stu-id="9972e-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
4.  <span data-ttu-id="9972e-134">Часть строки, называемая битовой картой NULL, зарезервирована для управления свойством столбцов содержать неопределенные значения.</span><span class="sxs-lookup"><span data-stu-id="9972e-134">Part of the row, known as the null bitmap, may be reserved to manage column nullability.</span></span> <span data-ttu-id="9972e-135">Вычислите ее размер.</span><span class="sxs-lookup"><span data-stu-id="9972e-135">Calculate its size:</span></span>  
  
     <span data-ttu-id="9972e-136">Если в ключе индекса есть столбцы, допускающие значения NULL, включая любые необходимые ключевые столбцы кластеризации, как описано в шаге 1.3, то часть строки индекса должна быть зарезервирована для битовой карты NULL.</span><span class="sxs-lookup"><span data-stu-id="9972e-136">If there are nullable columns in the index key, including any necessary clustering key columns as described in Step 1.3, part of the index row is reserved for the null bitmap.</span></span>  
  
     <span data-ttu-id="9972e-137">***Index_Null_Bitmap***  = 2 + ((количество столбцов в строке индекса + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="9972e-137">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="9972e-138">Следует использовать только целую часть предшествующего выражения.</span><span class="sxs-lookup"><span data-stu-id="9972e-138">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="9972e-139">Остаток должен быть отброшен.</span><span class="sxs-lookup"><span data-stu-id="9972e-139">Discard any remainder.</span></span>  
  
     <span data-ttu-id="9972e-140">Если нет ключевых столбцов, допускающих значения NULL, установите параметр ***Index_Null_Bitmap*** на 0.</span><span class="sxs-lookup"><span data-stu-id="9972e-140">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
5.  <span data-ttu-id="9972e-141">Вычислите размер данных переменной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-141">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="9972e-142">Если есть столбцы переменной длины в ключе индекса, включающие какие-либо необходимые кластеризованные индексные ключевые столбцы, определите, сколько пространства используется для хранения этих столбцов в строке индекса:</span><span class="sxs-lookup"><span data-stu-id="9972e-142">If there are variable-length columns in the index key, including any necessary clustered index key columns, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="9972e-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="9972e-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="9972e-144">Байты, добавляемые к ***Max_Var_Key_Size*** , предназначены для отслеживания каждого переменного столбца. В этой формуле предполагается, что все столбцы переменной длины заполнены на 100 процентов.</span><span class="sxs-lookup"><span data-stu-id="9972e-144">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="9972e-145">Если предполагается, что для хранения столбца переменной длины будет использовано меньше места, то для более точного подсчета общего размера таблицы можно задать значение ***Max_Var_Key_Size*** как процент от максимально возможной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-145">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="9972e-146">Если нет столбцов переменной ширины, установите значение ***Variable_Key_Size*** равным 0.</span><span class="sxs-lookup"><span data-stu-id="9972e-146">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="9972e-147">Расчет размера индексной строки:</span><span class="sxs-lookup"><span data-stu-id="9972e-147">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="9972e-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (для служебных данных строки заголовка индекса) + 6 (для указателя на идентификатор дочерней страницы)</span><span class="sxs-lookup"><span data-stu-id="9972e-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
7.  <span data-ttu-id="9972e-149">Расчет количества индексных строк на страницу (8 096 свободных байт на страницу):</span><span class="sxs-lookup"><span data-stu-id="9972e-149">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="9972e-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="9972e-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="9972e-151">Так как строка индекса не может быть разорвана на две страницы, общее количество строк индекса на странице необходимо округлить в меньшую сторону до ближайшего целого значения.</span><span class="sxs-lookup"><span data-stu-id="9972e-151">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="9972e-152">Значение 2 в формуле соответствует записи строки в массиве слота страницы.</span><span class="sxs-lookup"><span data-stu-id="9972e-152">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information-in-the-leaf-level"></a><span data-ttu-id="9972e-153">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="9972e-153">Step 2.</span></span> <span data-ttu-id="9972e-154">Расчет пространства, используемого для хранения данных индекса на конечном уровне</span><span class="sxs-lookup"><span data-stu-id="9972e-154">Calculate the Space Used to Store Index Information in the Leaf Level</span></span>  
 <span data-ttu-id="9972e-155">Используйте следующие шаги, чтобы оценить объем пространства, необходимый для хранения конечного уровня индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-155">You can use the following steps to estimate the amount of space that is required to store the leaf level of the index.</span></span> <span data-ttu-id="9972e-156">Для выполнения этого шага понадобятся значения, сохраненные на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9972e-156">You will need the values preserved from Step 1 to complete this step.</span></span>  
  
1.  <span data-ttu-id="9972e-157">Укажите количество столбцов переменой и фиксированной длины на конечном уровне и объем необходимого места для их хранения.</span><span class="sxs-lookup"><span data-stu-id="9972e-157">Specify the number of fixed-length and variable-length columns at the leaf level and calculate the space that is required for their storage:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9972e-158">Можно расширить некластеризованный индекс, включив неключевые столбцы в дополнение к ключевым столбцам индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-158">You can extend a nonclustered index by including nonkey columns in addition to the index key columns.</span></span> <span data-ttu-id="9972e-159">Эти дополнительные столбцы сохраняются только на конечном уровне некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-159">These additional columns are only stored at the leaf level of the nonclustered index.</span></span> <span data-ttu-id="9972e-160">Дополнительные сведения см. в статье [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="9972e-160">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9972e-161">Можно сочетать столбцы `varchar`, `nvarchar`, `varbinary` или `sql_variant`, в результате чего общая ширина определенной таблицы превысит 8060 байт.</span><span class="sxs-lookup"><span data-stu-id="9972e-161">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="9972e-162">Длина каждого из этих столбцов должна быть в пределах 8 000 байт для столбцов типа `varchar`, `varbinary` или `sql_variant` и 4 000 байт для столбцов типа `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="9972e-162">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="9972e-163">Тем не менее их общая ширина в таблице может превышать предел в 8 060 байт.</span><span class="sxs-lookup"><span data-stu-id="9972e-163">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span> <span data-ttu-id="9972e-164">Это также применимо к конечным строкам некластеризованного индекса, которые включают столбцы.</span><span class="sxs-lookup"><span data-stu-id="9972e-164">This also applies to nonclustered index leaf rows that have included columns.</span></span>  
  
     <span data-ttu-id="9972e-165">Если некластеризованный индекс не имеет никаких включенных столбцов, используйте значения из шага 1, включая любые модификации, определенные в шаге 1.3:</span><span class="sxs-lookup"><span data-stu-id="9972e-165">If the nonclustered index does not have any included columns, use the values from Step 1, including any modifications determined in Step 1.3:</span></span>  
  
     <span data-ttu-id="9972e-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="9972e-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span></span>  
  
     <span data-ttu-id="9972e-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="9972e-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span></span>  
  
     <span data-ttu-id="9972e-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="9972e-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span></span>  
  
     <span data-ttu-id="9972e-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="9972e-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="9972e-170">Если некластеризованный индекс имеет включенные столбцы, добавьте соответствующие значения к значениям из шага 1, включая любые модификации из шага 1.3.</span><span class="sxs-lookup"><span data-stu-id="9972e-170">If the nonclustered index does have included columns, add the appropriate values to the values from Step 1, including any modifications in Step 1.3.</span></span> <span data-ttu-id="9972e-171">Размер столбца зависит от типа данных и длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-171">The size of a column depends on the data type and length specification.</span></span> <span data-ttu-id="9972e-172">Дополнительные сведения см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9972e-172">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
     <span data-ttu-id="9972e-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + количество включенных столбцов</span><span class="sxs-lookup"><span data-stu-id="9972e-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + number of included columns</span></span>  
  
     <span data-ttu-id="9972e-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + общий размер в байтах всех включенных столбцов постоянной длины</span><span class="sxs-lookup"><span data-stu-id="9972e-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length included columns</span></span>  
  
     <span data-ttu-id="9972e-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + количество включенных столбцов переменной длины</span><span class="sxs-lookup"><span data-stu-id="9972e-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length included columns</span></span>  
  
     <span data-ttu-id="9972e-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + максимальный размер в байтах включенных столбцов переменной длины</span><span class="sxs-lookup"><span data-stu-id="9972e-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length included columns</span></span>  
  
2.  <span data-ttu-id="9972e-177">Учтите место для указателя на строку данных.</span><span class="sxs-lookup"><span data-stu-id="9972e-177">Account for the data row locator:</span></span>  
  
     <span data-ttu-id="9972e-178">Если некластеризованный индекс является неуникальным, то дополнительное место для указателя на строку данных уже было рассмотрено в шаге 1.3 и никаких дополнительных модификаций не требуется.</span><span class="sxs-lookup"><span data-stu-id="9972e-178">If the nonclustered index is nonunique, the overhead for the data row locator has already been considered in Step 1.3 and no additional modifications are required.</span></span> <span data-ttu-id="9972e-179">Переходите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="9972e-179">Go to the next step.</span></span>  
  
     <span data-ttu-id="9972e-180">Если некластеризованный индекс уникален, указатель на строку данных должен быть учтен во всех строках на конечном уровне.</span><span class="sxs-lookup"><span data-stu-id="9972e-180">If the nonclustered index is unique, the data row locator must be accounted for in all rows at the leaf level.</span></span>  
  
     <span data-ttu-id="9972e-181">Если некластеризованный индекс является индексом по куче, указателем на строку данных служит RID кучи (размером 8 байт).</span><span class="sxs-lookup"><span data-stu-id="9972e-181">If the nonclustered index is over a heap, the data row locator is the heap RID (size 8 bytes).</span></span>  
  
     <span data-ttu-id="9972e-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="9972e-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="9972e-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="9972e-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="9972e-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="9972e-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span></span>  
  
     <span data-ttu-id="9972e-185">Если некластеризованный индекс строится поверх кластеризованного, указателем строки данных является ключ кластеризации.</span><span class="sxs-lookup"><span data-stu-id="9972e-185">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="9972e-186">Столбцы, которые должны быть объединены с ключом некластеризованного индекса — это те столбцы в ключе кластеризации, которые еще не присутствуют в наборе ключевых столбцов некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-186">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="9972e-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + количество ключевых столбцов кластеризации, не вошедших в набор ключевых столбцов некластеризованного индекса (+ 1, если кластеризованный индекс неуникален)</span><span class="sxs-lookup"><span data-stu-id="9972e-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="9972e-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + число ключевых столбцов кластеризации фиксированной длины, не вошедших в набор ключевых столбцов некластеризованного индекса</span><span class="sxs-lookup"><span data-stu-id="9972e-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + number of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="9972e-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + число ключевых столбцов кластеризации переменной длины, не вошедших в набор ключевых столбцов некластеризованного индекса (+ 1, если кластеризованный индекс неуникален)</span><span class="sxs-lookup"><span data-stu-id="9972e-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="9972e-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + размер в байтах ключевых столбцов кластеризации переменной длины, не вошедших в набор ключевых столбцов некластеризованного индекса (+ 4, если кластеризованный индекс неуникален)</span><span class="sxs-lookup"><span data-stu-id="9972e-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + size in bytes of the variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
3.  <span data-ttu-id="9972e-191">Рассчет размера битовой карты NULL:</span><span class="sxs-lookup"><span data-stu-id="9972e-191">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="9972e-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="9972e-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="9972e-193">Следует использовать только целую часть предшествующего выражения.</span><span class="sxs-lookup"><span data-stu-id="9972e-193">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="9972e-194">Остаток должен быть отброшен.</span><span class="sxs-lookup"><span data-stu-id="9972e-194">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="9972e-195">Вычислите размер данных переменной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-195">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="9972e-196">Если есть столбцы переменной длины в ключе индекса, включая какие-либо необходимые ключевые столбцы кластеризации, как было описано в шаге 2.2, то определите, сколько пространства используется для хранения столбцов в строке индекса:</span><span class="sxs-lookup"><span data-stu-id="9972e-196">If there are variable-length columns in the index key, including any necessary clustering key columns as described previously in Step 2.2, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="9972e-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span><span class="sxs-lookup"><span data-stu-id="9972e-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span></span>  
  
     <span data-ttu-id="9972e-198">Байты, добавляемые к ***Max_Var_Key_Size*** , предназначены для отслеживания каждого переменного столбца. В этой формуле предполагается, что все столбцы переменной длины заполнены на 100 процентов.</span><span class="sxs-lookup"><span data-stu-id="9972e-198">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="9972e-199">Если предполагается, что для хранения столбца переменной длины будет использовано меньше места, то для более точного подсчета общего размера таблицы можно задать значение ***Max_Var_Leaf_Size*** как процент от максимально возможной длины.</span><span class="sxs-lookup"><span data-stu-id="9972e-199">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Leaf_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="9972e-200">Если в таблице нет столбцов переменной ширины, установите параметр ***Variable_Leaf_Size*** в 0.</span><span class="sxs-lookup"><span data-stu-id="9972e-200">If there are no variable-length columns, set ***Variable_Leaf_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="9972e-201">Расчет размера индексной строки:</span><span class="sxs-lookup"><span data-stu-id="9972e-201">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="9972e-202">***Leaf_Row_Size***   =  ***Fixed_Leaf_Size***  +  ***Variable_Leaf_Size***  +  ***Leaf_Null_Bitmap*** + 1 (для дополнительных затрат на заголовки строк в строке индекса) + 6 (для указателя на идентификатор дочерней страницы)</span><span class="sxs-lookup"><span data-stu-id="9972e-202">***Leaf_Row_Size***  = ***Fixed_Leaf_Size*** + ***Variable_Leaf_Size*** + ***Leaf_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="9972e-203">Расчет количества индексных строк на страницу (8 096 свободных байт на страницу):</span><span class="sxs-lookup"><span data-stu-id="9972e-203">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="9972e-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="9972e-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="9972e-205">Так как строка индекса не может быть разорвана на две страницы, общее количество строк индекса на странице необходимо округлить в меньшую сторону до ближайшего целого значения.</span><span class="sxs-lookup"><span data-stu-id="9972e-205">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="9972e-206">Значение 2 в формуле соответствует записи строки в массиве слота страницы.</span><span class="sxs-lookup"><span data-stu-id="9972e-206">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="9972e-207">Рассчет количества зарезервированных пустых строк на странице на основании указанного [коэффициента заполнения](../indexes/specify-fill-factor-for-an-index.md) :</span><span class="sxs-lookup"><span data-stu-id="9972e-207">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="9972e-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="9972e-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="9972e-209">Коэффициент заполнения, используемый в расчете, должен быть целым значением, а не процентным соотношением.</span><span class="sxs-lookup"><span data-stu-id="9972e-209">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="9972e-210">Так как строки не могут разрываться на разные страницы, общее количество строк на страницу необходимо округлить до меньшего целого значения целой строки.</span><span class="sxs-lookup"><span data-stu-id="9972e-210">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="9972e-211">При увеличении коэффициента заполнения на каждой странице будет сохранено больше данных и, соответственно, потребуется меньше страниц.</span><span class="sxs-lookup"><span data-stu-id="9972e-211">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="9972e-212">Значение 2 в формуле соответствует записи строки в массиве слота страницы.</span><span class="sxs-lookup"><span data-stu-id="9972e-212">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
8.  <span data-ttu-id="9972e-213">Вычислите количество страниц, необходимое для хранения всех строк:</span><span class="sxs-lookup"><span data-stu-id="9972e-213">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="9972e-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="9972e-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="9972e-215">Вычисленное количество страниц должно быть округлено в большую сторону до ближайшей целой страницы.</span><span class="sxs-lookup"><span data-stu-id="9972e-215">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
9. <span data-ttu-id="9972e-216">Расчет размера индекса (всего 8 192 байт на страницу).</span><span class="sxs-lookup"><span data-stu-id="9972e-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="9972e-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="9972e-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-3-calculate-the-space-used-to-store-index-information-in-the-non-leaf-levels"></a><span data-ttu-id="9972e-218">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="9972e-218">Step 3.</span></span> <span data-ttu-id="9972e-219">Расчет пространства, используемого для хранения данных индекса на неконечных уровнях</span><span class="sxs-lookup"><span data-stu-id="9972e-219">Calculate the Space Used to Store Index Information in the Non-leaf Levels</span></span>  
 <span data-ttu-id="9972e-220">Выполните эти шаги для оценки пространства, требуемого для хранения промежуточных и конечного уровней индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-220">Follow these steps to estimate the amount of space that is required to store the intermediate and root levels of the index.</span></span> <span data-ttu-id="9972e-221">Для выполнения этого шага понадобятся значения, сохраненные на шагах 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="9972e-221">You will need the values preserved from steps 2 and 3 to complete this step.</span></span>  
  
1.  <span data-ttu-id="9972e-222">Вычислите количество неконечных уровней индекса:</span><span class="sxs-lookup"><span data-stu-id="9972e-222">Calculate the number of non-leaf levels in the index:</span></span>  
  
     <span data-ttu-id="9972e-223">***Неконечные уровни*** = 1 + Index_Rows_Per_Page журнала (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="9972e-223">***Non-leaf Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="9972e-224">Данное значение округляется в большую сторону до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="9972e-224">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="9972e-225">Это значение не включает конечный уровень некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-225">This value does not include the leaf level of the nonclustered index.</span></span>  
  
2.  <span data-ttu-id="9972e-226">Вычислите количество неконечных страниц индекса:</span><span class="sxs-lookup"><span data-stu-id="9972e-226">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="9972e-227">***Num_Index_Pages*** = ∑ (уровень***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Level</sup>), где 1 <= уровень <= ***уровни***</span><span class="sxs-lookup"><span data-stu-id="9972e-227">***Num_Index_Pages***  = ∑Level (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Level</sup>)where 1 <= Level <= ***Levels***</span></span>  
  
     <span data-ttu-id="9972e-228">Округлите каждое слагаемое в большую сторону до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="9972e-228">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="9972e-229">Рассмотрим в качестве простого примера индекс, где ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="9972e-229">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="9972e-230">Первый уровень индекса над конечным уровнем содержит 1000 строк индекса, что составляет одну строку индекса на конечную страницу, а на одну страницу помещается 25 строк индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-230">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="9972e-231">Это означает, что для хранения этих 1000 строк индекса требуется 40 страниц.</span><span class="sxs-lookup"><span data-stu-id="9972e-231">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="9972e-232">Следующий уровень индекса должен хранить 40 строк.</span><span class="sxs-lookup"><span data-stu-id="9972e-232">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="9972e-233">Это означает, что ему необходимо 2 страницы.</span><span class="sxs-lookup"><span data-stu-id="9972e-233">This means that it requires 2 pages.</span></span> <span data-ttu-id="9972e-234">Последний уровень индекса должен хранить 2 строки.</span><span class="sxs-lookup"><span data-stu-id="9972e-234">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="9972e-235">Это означает, что ему необходима 1 страница.</span><span class="sxs-lookup"><span data-stu-id="9972e-235">This means that it requires 1 page.</span></span> <span data-ttu-id="9972e-236">Это соответствует 43 неконечным страницам индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-236">This yields 43 non-leaf index pages.</span></span> <span data-ttu-id="9972e-237">Использование этих значений в предыдущих формулах приводит к следующему результату:</span><span class="sxs-lookup"><span data-stu-id="9972e-237">When these numbers are used in the previous formulas, the result is as follows:</span></span>  
  
     <span data-ttu-id="9972e-238">***Не leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="9972e-238">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="9972e-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, то есть количество страниц, описываемых в примере.</span><span class="sxs-lookup"><span data-stu-id="9972e-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
3.  <span data-ttu-id="9972e-240">Расчет размера индекса (всего 8 192 байт на страницу).</span><span class="sxs-lookup"><span data-stu-id="9972e-240">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="9972e-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="9972e-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-4-total-the-calculated-values"></a><span data-ttu-id="9972e-242">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="9972e-242">Step 4.</span></span> <span data-ttu-id="9972e-243">Сложение полученных значений</span><span class="sxs-lookup"><span data-stu-id="9972e-243">Total the Calculated Values</span></span>  
 <span data-ttu-id="9972e-244">Необходимо сложить результаты, полученные на двух предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="9972e-244">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="9972e-245">Размер некластеризованного индекса (в байтах) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="9972e-245">Nonclustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="9972e-246">Этот расчет не учитывает следующие факторы.</span><span class="sxs-lookup"><span data-stu-id="9972e-246">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="9972e-247">Секционирование</span><span class="sxs-lookup"><span data-stu-id="9972e-247">Partitioning</span></span>  
  
     <span data-ttu-id="9972e-248">Размер служебных данных секционирования минимален, но его сложно рассчитать.</span><span class="sxs-lookup"><span data-stu-id="9972e-248">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="9972e-249">Он не столь важен, чтобы включать в расчеты.</span><span class="sxs-lookup"><span data-stu-id="9972e-249">It is not important to include.</span></span>  
  
-   <span data-ttu-id="9972e-250">Страницы размещения</span><span class="sxs-lookup"><span data-stu-id="9972e-250">Allocation pages</span></span>  
  
     <span data-ttu-id="9972e-251">Предусмотрена по меньшей мере одна IAM-страница, используемая для отслеживания страниц, выделенных куче, но размер служебных данных минимален, и алгоритма точного детерминированного вычисления количества используемых IAM-страниц не существует.</span><span class="sxs-lookup"><span data-stu-id="9972e-251">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="9972e-252">Значения LOB</span><span class="sxs-lookup"><span data-stu-id="9972e-252">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="9972e-253">Алгоритм точного определения места, используемого для хранения значений данных типа LOB `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` и `image` сложен.</span><span class="sxs-lookup"><span data-stu-id="9972e-253">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="9972e-254">Достаточно только сложить средние размеры ожидаемых значений больших объектов, умножить их на ***Num_Rows***и добавить его к общему размеру некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="9972e-254">It is sufficient to just add the average size of the LOB values expected, multiply by ***Num_Rows***, and add that to the total nonclustered index size.</span></span>  
  
-   <span data-ttu-id="9972e-255">Сжатие</span><span class="sxs-lookup"><span data-stu-id="9972e-255">Compression</span></span>  
  
     <span data-ttu-id="9972e-256">Размер сжатого индекса нельзя вычислить заранее.</span><span class="sxs-lookup"><span data-stu-id="9972e-256">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="9972e-257">Разреженные столбцы</span><span class="sxs-lookup"><span data-stu-id="9972e-257">Sparse columns</span></span>  
  
     <span data-ttu-id="9972e-258">Сведения о требованиях разреженных столбцов к месту на диске см. в разделе [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="9972e-258">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9972e-259">См. также:</span><span class="sxs-lookup"><span data-stu-id="9972e-259">See Also</span></span>  
 <span data-ttu-id="9972e-260">[Описания кластеризованных и некластеризованных индексов](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="9972e-260">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="9972e-261">[Создание некластеризованных индексов](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="9972e-261">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="9972e-262">[Создание кластеризованных индексов](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="9972e-262">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="9972e-263">[Оценка размера таблицы](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="9972e-263">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="9972e-264">[Оценка размера кластеризованного индекса](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="9972e-264">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="9972e-265">[Оценка размера кучи](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="9972e-265">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="9972e-266">Оценка размера базы данных</span><span class="sxs-lookup"><span data-stu-id="9972e-266">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
