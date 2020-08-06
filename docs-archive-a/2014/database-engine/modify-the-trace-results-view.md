---
title: Изменение представления результатов трассировки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 860a80dc-bac0-4ef0-bf7f-7a9b430d7aa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 050c8f179742cf3cef6473b03f062390caf195f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655902"
---
# <a name="modify-the-trace-results-view"></a><span data-ttu-id="e841a-102">Изменение представления результатов трассировки</span><span class="sxs-lookup"><span data-stu-id="e841a-102">Modify the Trace Results View</span></span>
  <span data-ttu-id="e841a-103">Данный раздел содержит описание процесса изменения представления результатов трассировки сеанса расширенных событий в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] посредством выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="e841a-103">This topic describes how to modify the trace results view of an Extended Events session in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] by performing the following tasks.</span></span>  
  
1.  [<span data-ttu-id="e841a-104">Добавление или удаление столбцов</span><span class="sxs-lookup"><span data-stu-id="e841a-104">Add or Remove Columns</span></span>](#AddRemoveColumns)  
  
2.  [<span data-ttu-id="e841a-105">Создание, редактирование или удаление объединенных столбцов</span><span class="sxs-lookup"><span data-stu-id="e841a-105">Create, Edit, or Delete Merged Columns</span></span>](#ChangeColumns)  
  
3.  [<span data-ttu-id="e841a-106">Сортировка результатов</span><span class="sxs-lookup"><span data-stu-id="e841a-106">Sort the Results</span></span>](#SortResults)  
  
4.  [<span data-ttu-id="e841a-107">Группирование результатов</span><span class="sxs-lookup"><span data-stu-id="e841a-107">Group the Results</span></span>](#GroupResults)  
  
5.  [<span data-ttu-id="e841a-108">Агрегатная обработка результатов</span><span class="sxs-lookup"><span data-stu-id="e841a-108">Aggregate the Results</span></span>](#AggregateResults)  
  
6.  [<span data-ttu-id="e841a-109">Фильтрация результатов</span><span class="sxs-lookup"><span data-stu-id="e841a-109">Filter the Results</span></span>](#Filter)  
  
7.  [<span data-ttu-id="e841a-110">Поиск текста в столбцах</span><span class="sxs-lookup"><span data-stu-id="e841a-110">Search for Text in Columns</span></span>](#Search)  
  
8.  [<span data-ttu-id="e841a-111">Изменение параметров отображения</span><span class="sxs-lookup"><span data-stu-id="e841a-111">Change the Display Settings</span></span>](#ChangeDisplay)  
  
##  <a name="add-or-remove-columns"></a><a name="AddRemoveColumns"></a><span data-ttu-id="e841a-112">Добавление или удаление столбцов</span><span class="sxs-lookup"><span data-stu-id="e841a-112">Add or Remove Columns</span></span>  
  
1.  <span data-ttu-id="e841a-113">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-113">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-114">Можно также щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Просмотр данных в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="e841a-114">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="e841a-115">В окне результатов трассировки щелкните правой кнопкой мыши заголовок столбца, а затем укажите **Выбрать столбец**.</span><span class="sxs-lookup"><span data-stu-id="e841a-115">In the trace results window, right-click the column header, and then select **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="e841a-116">В диалоговом окне **Выбрать столбец** в разделе **Доступные столбцы** выберите имена столбцов, которые необходимо добавить, а затем щелкните стрелку вправо.</span><span class="sxs-lookup"><span data-stu-id="e841a-116">In the **Choose Columns** dialog box, in the **Available columns** section, select the column names you want to add, and then click the right arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-117">По умолчанию столбцы упорядочиваются по имени.</span><span class="sxs-lookup"><span data-stu-id="e841a-117">By default, the columns are arranged by name.</span></span> <span data-ttu-id="e841a-118">Чтобы вывести на экран столбцы с учетом события, нажмите **Упорядочение по событиям**.</span><span class="sxs-lookup"><span data-stu-id="e841a-118">To display the columns by event, click **Arrange by event**.</span></span>  
  
     <span data-ttu-id="e841a-119">Чтобы удалить столбцы, укажите в разделе **Выбранные столбцы** те столбцы, которые необходимо удалить, и щелкните стрелку влево.</span><span class="sxs-lookup"><span data-stu-id="e841a-119">To remove columns, in the **Selected columns** section, select the columns you want to remove, and click the left arrow.</span></span>  
  
4.  <span data-ttu-id="e841a-120">В разделе **Выбранные столбцы** , чтобы изменить порядок отображения столбцов, нажмите кнопку **Переместить вверх** или **Переместить вниз** соответственно.</span><span class="sxs-lookup"><span data-stu-id="e841a-120">In the **Selected columns** section, to change the column order display, click **Move Up** or **Move Down** respectively.</span></span> <span data-ttu-id="e841a-121">Возможность перемещать сразу несколько строк не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="e841a-121">You cannot move multiple rows.</span></span>  
  
5.  <span data-ttu-id="e841a-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e841a-122">Click **OK**.</span></span>  
  
##  <a name="create-edit-or-delete-merged-columns"></a><a name="ChangeColumns"></a><span data-ttu-id="e841a-123">Создание, изменение и удаление Объединенных столбцов</span><span class="sxs-lookup"><span data-stu-id="e841a-123">Create, Edit, or Delete Merged Columns</span></span>  
  
#### <a name="to-create-merged-columns"></a><span data-ttu-id="e841a-124">Создание объединенных столбцов</span><span class="sxs-lookup"><span data-stu-id="e841a-124">To create merged columns</span></span>  
  
1.  <span data-ttu-id="e841a-125">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-125">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-126">Можно также щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Просмотр данных в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="e841a-126">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="e841a-127">В окне результатов трассировки щелкните правой кнопкой мыши заголовок столбца и выберите команду **Выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="e841a-127">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="e841a-128">В диалоговом окне **Выбрать столбцы** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e841a-128">In the **Choose Columns** dialog box, click **New**.</span></span>  
  
4.  <span data-ttu-id="e841a-129">В диалоговом окне **Создать объединенный столбец** в поле **Имя объединенного столбца** введите имя для объединенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="e841a-129">In the **New Merged Column** dialog box, in the **Merged column name** box, enter a name for the merged columns.</span></span>  
  
5.  <span data-ttu-id="e841a-130">В поле **Исходные объединяемые столбцы** выберите два или несколько столбцов, подлежащих объединению, из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e841a-130">In the **Original columns to merge** box, select two or more columns to merge from the drop-down list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-131">Подсистема обработки расширенных событий поддерживает объединение не больше пяти столбцов.</span><span class="sxs-lookup"><span data-stu-id="e841a-131">Extended Events only supports merging up to five columns.</span></span>  
  
6.  <span data-ttu-id="e841a-132">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e841a-132">Click **OK**.</span></span>  
  
#### <a name="to-edit-merged-columns"></a><span data-ttu-id="e841a-133">Изменение объединенных столбцов</span><span class="sxs-lookup"><span data-stu-id="e841a-133">To edit merged columns</span></span>  
  
1.  <span data-ttu-id="e841a-134">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-134">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-135">Можно также щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Просмотр данных в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="e841a-135">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="e841a-136">В окне результатов трассировки щелкните правой кнопкой мыши заголовок столбца и выберите команду **Выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="e841a-136">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="e841a-137">В диалоговом окне **Выбрать столбцы** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e841a-137">In the **Choose Columns** dialog box, click **Edit**.</span></span>  
  
4.  <span data-ttu-id="e841a-138">Чтобы изменить имя объединенного столбца, в диалоговом окне **Создать объединенный столбец** в поле **Имя объединенного столбца** введите новое имя.</span><span class="sxs-lookup"><span data-stu-id="e841a-138">To change the name of the merged column, in the **New Merged Column** dialog box, in the **Merged column name** box, enter the new name.</span></span>  
  
     <span data-ttu-id="e841a-139">Чтобы выбрать для объединения другие столбцы, в поле **Исходные объединяемые столбцы** выберите в раскрывающемся списке столбцы, которые должны быть объединены, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e841a-139">To change the columns you want to merge, in the **Original columns to merge** box, select the columns you want to merge from the drop-down list, and then click **OK**.</span></span>  
  
#### <a name="to-delete-merged-columns"></a><span data-ttu-id="e841a-140">Удаление объединенных столбцов</span><span class="sxs-lookup"><span data-stu-id="e841a-140">To delete merged columns</span></span>  
  
1.  <span data-ttu-id="e841a-141">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-141">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-142">Можно также щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Просмотр данных в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="e841a-142">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="e841a-143">В окне результатов трассировки щелкните правой кнопкой мыши заголовок столбца и выберите команду **Выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="e841a-143">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
3.  <span data-ttu-id="e841a-144">В диалоговом окне **Выбрать столбцы** выберите имя объединенного столбца, который необходимо удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e841a-144">In the **Choose Columns** dialog box, select the name of the merged column you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="sort-the-results"></a><a name="SortResults"></a><span data-ttu-id="e841a-145">Сортировка результатов</span><span class="sxs-lookup"><span data-stu-id="e841a-145">Sort the Results</span></span>  
  
#### <a name="to-sort-the-results-in-ascending-or-descending-order"></a><span data-ttu-id="e841a-146">Сортировка результатов по возрастанию или убыванию</span><span class="sxs-lookup"><span data-stu-id="e841a-146">To sort the results in ascending or descending order</span></span>  
  
-   <span data-ttu-id="e841a-147">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-147">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-148">Можно также щелкнуть правой кнопкой мыши имя сеанса, выбрать **Просмотр данных в режиме реального времени**и нажать кнопку « **прерывать поток данных** » на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="e841a-148">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
-   <span data-ttu-id="e841a-149">В окне результатов трассировки щелкните правой кнопкой мыши заголовок столбца, который необходимо отсортировать.</span><span class="sxs-lookup"><span data-stu-id="e841a-149">In the trace results window, right-click the column heading you want to sort.</span></span> <span data-ttu-id="e841a-150">Щелкните **Сортировать по возрастанию** или **Сортировать по убыванию** , чтобы выполнить сортировку столбца по возрастанию или убыванию соответственно.</span><span class="sxs-lookup"><span data-stu-id="e841a-150">Click **Sort Ascending** or **Sort Descending** to sort the column in ascending or descending order respectively.</span></span>  
  
     <span data-ttu-id="e841a-151">Если имеются сгруппированные столбцы, то сортировка столбца приводит лишь к сортировке данных в пределах группы.</span><span class="sxs-lookup"><span data-stu-id="e841a-151">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
##  <a name="group-results"></a><a name="GroupResults"></a><span data-ttu-id="e841a-152">Результаты группы</span><span class="sxs-lookup"><span data-stu-id="e841a-152">Group Results</span></span>  
  
#### <a name="to-group-the-results-by-a-single-column"></a><span data-ttu-id="e841a-153">Группирование результатов по одному столбцу</span><span class="sxs-lookup"><span data-stu-id="e841a-153">To group the results by a single column</span></span>  
  
1.  <span data-ttu-id="e841a-154">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-154">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-155"> Можно также щелкнуть правой кнопкой мыши имя сеанса, выбрать **Просмотр данных, передаваемых в режиме реального времени**и нажать кнопку **Остановить поток данных** на панели инструментов «Расширенные события».</span><span class="sxs-lookup"><span data-stu-id="e841a-155">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the Extended Events toolbar.</span></span>  
  
2.  <span data-ttu-id="e841a-156">В окне результатов трассировки щелкните правой кнопкой мыши заголовок столбца, по которому должно быть выполнено группирование, а затем выберите команду **Группировать по этому столбцу**.</span><span class="sxs-lookup"><span data-stu-id="e841a-156">In the trace results window, right-click the column header you want to group, and then click **Group By This Column**.</span></span>  
  
#### <a name="to-group-the-results-by-multiple-columns"></a><span data-ttu-id="e841a-157">Группирование результатов по нескольким столбцам</span><span class="sxs-lookup"><span data-stu-id="e841a-157">To group the results by multiple columns</span></span>  
  
1.  <span data-ttu-id="e841a-158">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-158">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-159">Можно также щелкнуть правой кнопкой мыши имя сеанса, выбрать **Просмотр данных в режиме реального времени**и нажать кнопку « **прерывать поток данных** » на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="e841a-159">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
2.  <span data-ttu-id="e841a-160">На панели инструментов «Расширенные события» нажмите кнопку **Группирование** .</span><span class="sxs-lookup"><span data-stu-id="e841a-160">Click the **Grouping** button on the Extended Events toolbar.</span></span>  
  
3.  <span data-ttu-id="e841a-161">В диалоговом окне **Группирование** в поле **Доступные столбцы** выберите столбцы, которые необходимо сгруппировать, а затем щелкните стрелку вправо.</span><span class="sxs-lookup"><span data-stu-id="e841a-161">In the **Grouping** dialog box, in the **Available columns** box, select the columns you want to group, and then click the right arrow.</span></span>  
  
     <span data-ttu-id="e841a-162">Изменить порядок группирования можно стрелками вверх и вниз в разделе **Столбцы, сгруппированные по** .</span><span class="sxs-lookup"><span data-stu-id="e841a-162">To change the grouping order, in the **Columns grouped on** section, click the up or down arrows.</span></span>  
  
     <span data-ttu-id="e841a-163">Чтобы удалить столбцы из группирования, в поле **Столбцы, сгруппированные по** выберите столбцы, которые требуется удалить, а затем щелкните стрелку влево.</span><span class="sxs-lookup"><span data-stu-id="e841a-163">To remove columns from the grouping, in the **Columns grouped on** box, select the columns you want to remove and then click the left arrow.</span></span>  
  
4.  <span data-ttu-id="e841a-164">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e841a-164">Click **OK**.</span></span>  
  
##  <a name="aggregate-results"></a><a name="AggregateResults"></a><span data-ttu-id="e841a-165">Статистические результаты</span><span class="sxs-lookup"><span data-stu-id="e841a-165">Aggregate Results</span></span>  
 <span data-ttu-id="e841a-166">Расширенные события поддерживают пять агрегатных функций:</span><span class="sxs-lookup"><span data-stu-id="e841a-166">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="e841a-167">Sum</span><span class="sxs-lookup"><span data-stu-id="e841a-167">Sum</span></span>  
  
-   <span data-ttu-id="e841a-168">Min</span><span class="sxs-lookup"><span data-stu-id="e841a-168">Min</span></span>  
  
-   <span data-ttu-id="e841a-169">Max</span><span class="sxs-lookup"><span data-stu-id="e841a-169">Max</span></span>  
  
-   <span data-ttu-id="e841a-170">Среднее</span><span class="sxs-lookup"><span data-stu-id="e841a-170">Average</span></span>  
  
-   <span data-ttu-id="e841a-171">Count</span><span class="sxs-lookup"><span data-stu-id="e841a-171">Count</span></span>  
  
 <span data-ttu-id="e841a-172">Функции Sum, Min, Max и Average можно использовать только для доступных числовых столбцов.</span><span class="sxs-lookup"><span data-stu-id="e841a-172">Sum, Min,  Max, and Average can only be used with available numeric columns.</span></span> <span data-ttu-id="e841a-173">Count — это количество не равных NULL значений, имеющихся в выбранном столбце в группе.</span><span class="sxs-lookup"><span data-stu-id="e841a-173">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
#### <a name="to-aggregate-results"></a><span data-ttu-id="e841a-174">Агрегатная обработка результатов</span><span class="sxs-lookup"><span data-stu-id="e841a-174">To aggregate results</span></span>  
  
1.  <span data-ttu-id="e841a-175">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-175">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-176">Можно также щелкнуть правой кнопкой мыши имя сеанса, выбрать **Просмотр данных в режиме реального времени**и нажать кнопку « **прерывать поток данных** » на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="e841a-176">You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-177">Агрегатная обработка осуществляется по отношению к группе, поэтому необходимо сгруппировать результаты, прежде чем появится возможность выполнить статистическую обработку.</span><span class="sxs-lookup"><span data-stu-id="e841a-177">Aggregation is run against a group, so you must group the results before you can perform the aggregation.</span></span>  
  
2.  <span data-ttu-id="e841a-178">На панели инструментов «Расширенные события» нажмите кнопку **Выполнять статистическое вычисление** .</span><span class="sxs-lookup"><span data-stu-id="e841a-178">On the Extended Events toolbar, click the **Aggregate** button.</span></span>  
  
     <span data-ttu-id="e841a-179">Откроется диалоговое окно **Статистическая обработка** , отображающее столбцы, доступные для статистической обработки.</span><span class="sxs-lookup"><span data-stu-id="e841a-179">The **Aggregation** dialog box appears displaying the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="e841a-180">В области **Тип статистической обработки**выберите в раскрывающемся списке тип статистической обработки соответствующего столбца.</span><span class="sxs-lookup"><span data-stu-id="e841a-180">Under **Aggregation Type**, select how you want to aggregate the corresponding column from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="e841a-181">В поле **Сортировать результаты статистической обработки по** выберите в раскрывающемся списке столбец, по которому должна быть выполнена сортировка.</span><span class="sxs-lookup"><span data-stu-id="e841a-181">In the **Sort aggregation by** box, select the column you want to sort by from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="e841a-182">Выберите вариант **В порядке возрастания** , чтобы отсортировать результаты статистической обработки в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="e841a-182">Select the **In ascending order** option to sort the aggregation result in ascending order.</span></span>  
  
6.  <span data-ttu-id="e841a-183">Выберите вариант **В порядке убывания** , чтобы отсортировать результаты агрегатной обработки в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="e841a-183">Select the **In descending order** option to sort the aggregation result in descending order.</span></span>  
  
7.  <span data-ttu-id="e841a-184">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e841a-184">Click **OK**.</span></span>  
  
##  <a name="filter-results"></a><a name="Filter"></a><span data-ttu-id="e841a-185">Фильтрация результатов</span><span class="sxs-lookup"><span data-stu-id="e841a-185">Filter Results</span></span>  
 <span data-ttu-id="e841a-186">Для уменьшения объемов результатов, отображаемых в окне трассировки, можно применить фильтры.</span><span class="sxs-lookup"><span data-stu-id="e841a-186">You can apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="e841a-187">Фильтр отображения включает в себя фильтр времени и расширенный фильтр.</span><span class="sxs-lookup"><span data-stu-id="e841a-187">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="e841a-188">Для фильтрации результатов трассировки по отметкам времени событий используется фильтр времени, а для создания условий фильтра с использованием полей события и действий — дополнительный фильтр.</span><span class="sxs-lookup"><span data-stu-id="e841a-188">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="e841a-189">Между фильтрами времени и дополнительными фильтрами определено отношение И.</span><span class="sxs-lookup"><span data-stu-id="e841a-189">There is an logical AND relationship between the Time and Advanced Filters.</span></span>  
  
#### <a name="to-create-a-filter"></a><span data-ttu-id="e841a-190">Создание фильтра</span><span class="sxs-lookup"><span data-stu-id="e841a-190">To create a filter</span></span>  
  
1.  <span data-ttu-id="e841a-191">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-191">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-192">Можно также щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Просмотр данных в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="e841a-192">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="e841a-193">В окне результатов трассировки выберите результаты, которые необходимо отфильтровать, а затем на панели инструментов «Расширенные события» щелкните **Фильтры** .</span><span class="sxs-lookup"><span data-stu-id="e841a-193">In the trace results window, select the results you want to filter, and then on the Extended Events toolbar, click the **Filters** button.</span></span>  
  
3.  <span data-ttu-id="e841a-194">В диалоговом окне **Фильтры** выберите **Задать фильтр времени** , чтобы установить фильтр времени, перетаскивая ползунки для задания временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="e841a-194">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars to set the timeline.</span></span> <span data-ttu-id="e841a-195">Обратите внимание, что после ввода значения времени происходит перемещение левого ползунка времени соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e841a-195">Note that when you move the slider bars, the time box displays the time value accordingly.</span></span> <span data-ttu-id="e841a-196">Можно также ввести значение времени в поле времени или выбрать его из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e841a-196">You can also enter the time in the time boxes, or you select it from the drop-down list.</span></span> <span data-ttu-id="e841a-197">Обратите внимание, что после ввода значения времени происходит перемещение левого ползунка времени соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e841a-197">Note that when you enter the time, the left time slider will move accordingly.</span></span>  
  
4.  <span data-ttu-id="e841a-198">В разделе **Дополнительные фильтры** примените критерии фильтра и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e841a-198">In the **Additional Filters** section, apply your filter criteria, and then click **Apply**.</span></span> <span data-ttu-id="e841a-199">После завершения создания фильтра нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e841a-199">When your finished created the filter, click **OK**.</span></span>  
  
 <span data-ttu-id="e841a-200">Особым случаем является совпадение имени поля события с именем действия.</span><span class="sxs-lookup"><span data-stu-id="e841a-200">A special situation is when an event field has the same name as an action.</span></span> <span data-ttu-id="e841a-201">Примером служит session_id.</span><span class="sxs-lookup"><span data-stu-id="e841a-201">An example of this would be session_id.</span></span> <span data-ttu-id="e841a-202">В некоторые события входит поле session_id, а также можно добавить действие session_id.</span><span class="sxs-lookup"><span data-stu-id="e841a-202">There are several events that include a session_id field and you could also add the session_id action.</span></span> <span data-ttu-id="e841a-203">Оба фрагмента данных собираются, но в сетке отображения профилировщика расширенных событий применяется следующая логика.</span><span class="sxs-lookup"><span data-stu-id="e841a-203">Both pieces of information are collected, but the Extended Events profiler display grid uses the following logic.</span></span>  
  
-   <span data-ttu-id="e841a-204">В сетке отображается только одна копия столбца (в данном случае session_id).</span><span class="sxs-lookup"><span data-stu-id="e841a-204">Only one copy of the column (session_id in this case) is shown in the grid display.</span></span>  
  
-   <span data-ttu-id="e841a-205">Если в данных существуют и поле и действие, то отображается значение поля.</span><span class="sxs-lookup"><span data-stu-id="e841a-205">If both fields and action exist in the data, the field value is shown.</span></span>  
  
-   <span data-ttu-id="e841a-206">Если в данных существует или только действие, или только поле, то отображается это действие или это поле.</span><span class="sxs-lookup"><span data-stu-id="e841a-206">If only field or action is exists in the data, the field or action is displayed.</span></span>  
  
-   <span data-ttu-id="e841a-207">Если не существует ни действия, ни поля, отображается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e841a-207">If neither action nor field exists, display NULL.</span></span>  
  
##  <a name="search-for-text-in-columns"></a><a name="Search"></a><span data-ttu-id="e841a-208">Поиск текста в столбцах</span><span class="sxs-lookup"><span data-stu-id="e841a-208">Search for Text in Columns</span></span>  
  
1.  <span data-ttu-id="e841a-209">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-209">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-210">Можно также щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Просмотр данных в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="e841a-210">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="e841a-211">На панели инструментов «Расширенные события» нажмите кнопку **Поиск** .</span><span class="sxs-lookup"><span data-stu-id="e841a-211">On the Extended Events toolbar, click the **Find** button.</span></span>  
  
3.  <span data-ttu-id="e841a-212">В диалоговом окне **Найти в расширенных событиях** в поле **Найти** введите текст для поиска.</span><span class="sxs-lookup"><span data-stu-id="e841a-212">In the **Find in Extended Events** dialog box, in the **Find what** box, enter the text you want to search for.</span></span>  
  
     <span data-ttu-id="e841a-213">В раскрывающемся списке можно выбрать одну из 20 последних строк поиска.</span><span class="sxs-lookup"><span data-stu-id="e841a-213">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="e841a-214">В поле **Искать в** выберите в раскрывающемся списке расположение, где должен осуществляться поиск указанного текста.</span><span class="sxs-lookup"><span data-stu-id="e841a-214">In the **Look in** box, select the location in which to search for the specified text from the drop-down list.</span></span> <span data-ttu-id="e841a-215">Можно использовать следующие параметры для поиска:</span><span class="sxs-lookup"><span data-stu-id="e841a-215">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="e841a-216">**Столбцы таблицы**.</span><span class="sxs-lookup"><span data-stu-id="e841a-216">**Table Columns**.</span></span> <span data-ttu-id="e841a-217">Этот параметр служит для поиска всех видимых столбцов в окне трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-217">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="e841a-218">**Подробные сведения**.</span><span class="sxs-lookup"><span data-stu-id="e841a-218">**Details**.</span></span> <span data-ttu-id="e841a-219">Этот параметр используется для поиска в окне трассировки всех столбцов (повышенных и неповышенных), которые были выбраны перед открытием диалогового окна **найти в расширенных событиях** .</span><span class="sxs-lookup"><span data-stu-id="e841a-219">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="e841a-220">**\<Event column name>**.</span><span class="sxs-lookup"><span data-stu-id="e841a-220">**\<Event column name>**.</span></span> <span data-ttu-id="e841a-221">Этот параметр служит для поиска в столбце определенного события из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e841a-221">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="e841a-222">Чтобы указать, как должен быть определен поиск, можно также задать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e841a-222">Use the following options to specify how you want to define the search:</span></span>  
  
    1.  <span data-ttu-id="e841a-223">**Учитывать регистр**.</span><span class="sxs-lookup"><span data-stu-id="e841a-223">**Match case**.</span></span> <span data-ttu-id="e841a-224">Используйте этот параметр, чтобы отобразить результаты поиска для текста, введенного в поле **найти** , совпадающие как по содержимому, так и по регистру.</span><span class="sxs-lookup"><span data-stu-id="e841a-224">Use this option to display the search results for the text you entered in the **Find what** box that are matched both by content and by case.</span></span>  
  
    2.  <span data-ttu-id="e841a-225">**Слово целиком**.</span><span class="sxs-lookup"><span data-stu-id="e841a-225">**Match whole word**.</span></span> <span data-ttu-id="e841a-226">Этот параметр служит для отображения результатов поиска введенного текста, которые согласуются с полными словами.</span><span class="sxs-lookup"><span data-stu-id="e841a-226">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    3.  <span data-ttu-id="e841a-227">**Поиск**.</span><span class="sxs-lookup"><span data-stu-id="e841a-227">**Search up**.</span></span> <span data-ttu-id="e841a-228">Этот параметр используется для поиска от местоположения курсора к началу результатов.</span><span class="sxs-lookup"><span data-stu-id="e841a-228">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    4.  <span data-ttu-id="e841a-229">**Используйте**.</span><span class="sxs-lookup"><span data-stu-id="e841a-229">**Use**.</span></span> <span data-ttu-id="e841a-230">Используйте этот параметр для интерпретации специальных символов и регулярных выражений, введенных в поле **найти** .</span><span class="sxs-lookup"><span data-stu-id="e841a-230">Use this option to interpret the special characters and the regular expressions you entered in the **Find what** box.</span></span> <span data-ttu-id="e841a-231">Специальные символы — это символы-шаблоны (\*) и (?), представляющие один или нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="e841a-231">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="e841a-232">Регулярные выражения представляют собой специальные обозначения, используемые для определения искомого текста с помощью шаблонов.</span><span class="sxs-lookup"><span data-stu-id="e841a-232">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
6.  <span data-ttu-id="e841a-233">Щелкните **Найти далее** , чтобы найти следующее вхождение текста, введенного в поле **Найти** .</span><span class="sxs-lookup"><span data-stu-id="e841a-233">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
##  <a name="change-the-display-settings"></a><a name="ChangeDisplay"></a><span data-ttu-id="e841a-234">Изменение параметров экрана</span><span class="sxs-lookup"><span data-stu-id="e841a-234">Change the Display Settings</span></span>  
 <span data-ttu-id="e841a-235">Можно сохранить сведения о столбцах (порядок столбцов, объединенный столбец и ширина столбца) и отфильтрованные результаты трассировки в файле параметров представления «Расширенные события» (VIEWSETTING-файл).</span><span class="sxs-lookup"><span data-stu-id="e841a-235">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="e841a-236">После сохранения файла можно его использовать для трассировки результатов и изменения представления.</span><span class="sxs-lookup"><span data-stu-id="e841a-236">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
#### <a name="to-change-the-display-settings"></a><span data-ttu-id="e841a-237">Изменение параметров отображения</span><span class="sxs-lookup"><span data-stu-id="e841a-237">To change the display settings</span></span>  
  
1.  <span data-ttu-id="e841a-238">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="e841a-238">Open a .XEL file to view the trace results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e841a-239">Можно также щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Просмотр данных в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="e841a-239">You can also right click the session name, and then select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="e841a-240">В окне результатов трассировки панели или в меню «Расширенные события» выберите **Параметры экрана**.</span><span class="sxs-lookup"><span data-stu-id="e841a-240">In the trace results window, on the Extended Events toolbar or menu, select **Display Settings**.</span></span>  
  
3.  <span data-ttu-id="e841a-241">Выберите один из следующих параметров из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e841a-241">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="e841a-242">**Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="e841a-242">**Save as**.</span></span> <span data-ttu-id="e841a-243">Сохраните столбцы и сведения о результатах трассировки в файле .viewsetting.</span><span class="sxs-lookup"><span data-stu-id="e841a-243">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="e841a-244">**Откройте**.</span><span class="sxs-lookup"><span data-stu-id="e841a-244">**Open**.</span></span> <span data-ttu-id="e841a-245">Открыть существующий VIEWSETTING-файл.</span><span class="sxs-lookup"><span data-stu-id="e841a-245">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="e841a-246">**Откройте последние**.</span><span class="sxs-lookup"><span data-stu-id="e841a-246">**Open recent**.</span></span> <span data-ttu-id="e841a-247">Открыть недавно сохраненный VIEWSETTING-файл.</span><span class="sxs-lookup"><span data-stu-id="e841a-247">Open a recently saved .viewsetting file.</span></span>  
  
  
