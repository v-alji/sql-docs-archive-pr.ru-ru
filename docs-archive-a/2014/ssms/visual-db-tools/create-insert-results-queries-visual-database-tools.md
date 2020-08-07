---
title: Создание запросов на вставку результатов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- result sets [SQL Server], queries
- results [SQL Server], query
- Insert Results query
- queries [SQL Server], results
ms.assetid: 8770d630-09cc-47ec-a0e9-e9de2d7bbc89
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02643c2cf3295debe740a696941f8730d4417254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731286"
---
# <a name="create-insert-results-queries-visual-database-tools"></a><span data-ttu-id="ddac4-102">Создание запросов на вставку результатов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="ddac4-102">Create Insert Results Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="ddac4-103">Запрос вставки результатов позволяет копировать строки внутри таблицы или из одной таблицы в другую.</span><span class="sxs-lookup"><span data-stu-id="ddac4-103">You can copy rows from one table to another or within a table using an Insert Results query.</span></span> <span data-ttu-id="ddac4-104">Например, с помощью запроса вставки результатов можно скопировать сведения о названиях книг некоторого издателя из таблицы `titles` в другую таблицу, которая будет ему доступна.</span><span class="sxs-lookup"><span data-stu-id="ddac4-104">For example, in a `titles` table, you can use an Insert Results query to copy information about all the titles for one publisher to a second table that you can make available to that publisher.</span></span> <span data-ttu-id="ddac4-105">Запрос вставки результатов похож на запрос создания таблицы, но копирует строки в уже существующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="ddac4-105">An Insert Results query is similar to Make Table Queries, but copies rows into an existing table.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="ddac4-106">Строки можно скопировать из одной таблицы в другую методом вырезания и вставки.</span><span class="sxs-lookup"><span data-stu-id="ddac4-106">You can also copy rows from one table to another using cut and paste.</span></span> <span data-ttu-id="ddac4-107">Создайте запрос для каждой таблицы и запустите их.</span><span class="sxs-lookup"><span data-stu-id="ddac4-107">Create a query for each table and run the queries.</span></span> <span data-ttu-id="ddac4-108">Скопируйте нужные строки из одной сетки результатов в другую.</span><span class="sxs-lookup"><span data-stu-id="ddac4-108">Copy the rows you want from one results grid to the other.</span></span>  
  
 <span data-ttu-id="ddac4-109">При создании запроса вставки результатов необходимо указать следующее.</span><span class="sxs-lookup"><span data-stu-id="ddac4-109">When you create an Insert Results query, you specify:</span></span>  
  
-   <span data-ttu-id="ddac4-110">Таблицу базы данных, куда нужно скопировать строки (целевую таблицу).</span><span class="sxs-lookup"><span data-stu-id="ddac4-110">The database table to copy rows to (the destination table).</span></span>  
  
-   <span data-ttu-id="ddac4-111">Таблицу или таблицы, из которых копируются строки (исходную таблицу).</span><span class="sxs-lookup"><span data-stu-id="ddac4-111">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="ddac4-112">Исходная таблица или таблицы становятся частью вложенного запроса.</span><span class="sxs-lookup"><span data-stu-id="ddac4-112">The source table or tables become part of a subquery.</span></span> <span data-ttu-id="ddac4-113">При копировании данных внутри таблицы целевая таблица совпадает с исходной.</span><span class="sxs-lookup"><span data-stu-id="ddac4-113">If you are copying within a table, the source table is the same as the destination table.</span></span>  
  
-   <span data-ttu-id="ddac4-114">Столбцы в исходной таблице, содержимое которых нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="ddac4-114">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="ddac4-115">Столбцы в целевой таблице, в которые нужно скопировать данные.</span><span class="sxs-lookup"><span data-stu-id="ddac4-115">The target columns in the destination table to copy the data to.</span></span>  
  
-   <span data-ttu-id="ddac4-116">Условия поиска для выборки строк, которые нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="ddac4-116">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="ddac4-117">Порядок сортировки, когда нужно скопировать строки в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="ddac4-117">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="ddac4-118">Параметры группировки для случаев, когда нужно скопировать только сводные данные.</span><span class="sxs-lookup"><span data-stu-id="ddac4-118">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="ddac4-119">Например, следующий запрос копирует сведения о названиях книг из таблицы `titles` в архивную таблицу `archivetitles`.</span><span class="sxs-lookup"><span data-stu-id="ddac4-119">For example, the following query copies title information from the `titles` table to an archive table called `archivetitles`.</span></span> <span data-ttu-id="ddac4-120">Запрос копирует содержимое четырех столбцов для всех названий, принадлежащих указанному издателю:</span><span class="sxs-lookup"><span data-stu-id="ddac4-120">The query copies the contents of four columns for all titles belonging to a particular publisher:</span></span>  
  
```  
INSERT INTO archivetitles   
   (title_id, title, type, pub_id)  
SELECT title_id, title, type, pub_id  
FROM titles  
WHERE (pub_id = '0766')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ddac4-121">Чтобы вставить значения в новую строку, используйте запрос вставки значений.</span><span class="sxs-lookup"><span data-stu-id="ddac4-121">To insert values into a new row, use an Insert Values query.</span></span>  
  
 <span data-ttu-id="ddac4-122">Можно скопировать содержимое всех или только выбранных столбцов в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="ddac4-122">You can copy the contents of selected columns or of all columns in a row.</span></span> <span data-ttu-id="ddac4-123">В любом случае, копируемые данные должны быть совместимы со столбцами целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="ddac4-123">In either case, the data you are copying must be compatible with the columns in the rows you are copying to.</span></span> <span data-ttu-id="ddac4-124">Например, при копировании содержимого столбца `price`столбец, куда копируются данные, должен допускать числовые данные с десятичным разделителем.</span><span class="sxs-lookup"><span data-stu-id="ddac4-124">For example, if you copy the contents of a column such as `price`, the column in the row you are copying to must accept numeric data with decimal places.</span></span> <span data-ttu-id="ddac4-125">При копировании всей строки физическое положение совместимых столбцов целевой и исходной таблицы должно совпадать.</span><span class="sxs-lookup"><span data-stu-id="ddac4-125">If you are copying an entire row, the destination table must have compatible columns in the same physical position as the source table.</span></span>  
  
 <span data-ttu-id="ddac4-126">При создании запроса вставки результатов внешний вид панели критериев меняется, отражая параметры, доступные для копирования данных.</span><span class="sxs-lookup"><span data-stu-id="ddac4-126">When you create an Insert Results query, the Criteria pane changes to reflect options available for copying data.</span></span> <span data-ttu-id="ddac4-127">Добавляется столбец «Добавить» позволяющий указать столбцы, в которые необходимо скопировать данные.</span><span class="sxs-lookup"><span data-stu-id="ddac4-127">An Append column is added to allow you to specify the columns into which data should be copied.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="ddac4-128">Результат выполнения запроса вставки результатов отменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="ddac4-128">You cannot undo the action of executing an Insert Results query.</span></span> <span data-ttu-id="ddac4-129">В целях предосторожности создайте резервную копию данных перед выполнением запроса.</span><span class="sxs-lookup"><span data-stu-id="ddac4-129">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-results-query"></a><span data-ttu-id="ddac4-130">Создание запроса вставки результатов</span><span class="sxs-lookup"><span data-stu-id="ddac4-130">To create an Insert Results query</span></span>  
  
1.  <span data-ttu-id="ddac4-131">Создайте новый запрос и добавьте таблицу, из которой нужно скопировать строки (исходную таблицу).</span><span class="sxs-lookup"><span data-stu-id="ddac4-131">Create a new query and add the table from which you want to copy rows (the source table).</span></span> <span data-ttu-id="ddac4-132">При копировании строк внутри таблицы в качестве целевой таблицы нужно указать исходную.</span><span class="sxs-lookup"><span data-stu-id="ddac4-132">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
2.  <span data-ttu-id="ddac4-133">В меню **Конструктор запросов** выберите пункт **Тип изменения**, а затем пункт **Вставить результаты**.</span><span class="sxs-lookup"><span data-stu-id="ddac4-133">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
3.  <span data-ttu-id="ddac4-134">В диалоговом окне [Выбор целевой таблицы для инструкции Insert Results](visual-database-tools.md)выберите таблицу, в которую нужно скопировать строки (целевую таблицу).</span><span class="sxs-lookup"><span data-stu-id="ddac4-134">In the [Choose Target Table for Insert Results Dialog Box](visual-database-tools.md), select the table to copy rows to (the destination table).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ddac4-135">Конструктор запросов и представлений не может заранее определить, какие таблицы и представления можно обновить.</span><span class="sxs-lookup"><span data-stu-id="ddac4-135">The Query and View Designer cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="ddac4-136">Поэтому список **Имя таблицы** в диалоговом окне **Выбор целевой таблицы для вставки результатов** содержит все доступные таблицы и представления в запрашиваемом подключении к данным (даже те, в которые нельзя скопировать строки).</span><span class="sxs-lookup"><span data-stu-id="ddac4-136">Therefore, the **Table Name** list in the **Choose Table for Insert From Query** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
4.  <span data-ttu-id="ddac4-137">В прямоугольнике, представляющем таблицу или возвращающий табличное значение объект, выберите имена столбцов, содержимое которых нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="ddac4-137">In the rectangle representing the table or table-valued object, choose the names of the columns whose contents you want to copy.</span></span> <span data-ttu-id="ddac4-138">Чтобы скопировать целые строки, выберите \*\* \* (все столбцы)\*\*.</span><span class="sxs-lookup"><span data-stu-id="ddac4-138">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="ddac4-139">Конструктор запросов и представлений добавляет выбранные столбцы к столбцу **Столбец** панели критериев.</span><span class="sxs-lookup"><span data-stu-id="ddac4-139">The Query and View Designer adds the columns you choose to the **Column** column of the Criteriapane.</span></span>  
  
5.  <span data-ttu-id="ddac4-140">В столбце **Добавить** на панели критериев выберите столбец в целевой таблице для каждого копируемого столбца исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="ddac4-140">In the **Append** column of the Criteria pane, select a target column in the destination table for each column you are copying.</span></span> <span data-ttu-id="ddac4-141">Выберите \*TableName. \* \* при копировании целых строк.</span><span class="sxs-lookup"><span data-stu-id="ddac4-141">Choose *tablename.\** if you are copying entire rows.</span></span> <span data-ttu-id="ddac4-142">Столбцы в исходной и целевой таблице должны иметь одинаковые или совместимые типы данных.</span><span class="sxs-lookup"><span data-stu-id="ddac4-142">The columns in the destination table must have the same (or compatible) data types as the columns in the source table.</span></span>  
  
6.  <span data-ttu-id="ddac4-143">Чтобы скопировать строки в определенном порядке, укажите порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="ddac4-143">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="ddac4-144">Дополнительные сведения см. в разделе [Результаты запросов сортировки и группирования (визуальные инструменты для баз данных)](sort-and-group-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ddac4-144">For details, see [Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md).</span></span>  
  
7.  <span data-ttu-id="ddac4-145">Укажите копируемые строки путем ввода условий поиска в столбце **Фильтр** .</span><span class="sxs-lookup"><span data-stu-id="ddac4-145">Specify the rows to copy by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="ddac4-146">Дополнительные сведения см. в разделе [Определение критериев поиска (визуальные инструменты для баз данных)](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ddac4-146">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="ddac4-147">Если условия поиска не заданы, в целевую таблицу будут скопированы все строки исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="ddac4-147">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ddac4-148">При добавления столбца для поиска на панели критериев конструктор запросов и представлений также включит его в список столбцов, подлежащих копированию.</span><span class="sxs-lookup"><span data-stu-id="ddac4-148">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="ddac4-149">Если столбец нужно использовать только для поиска, но не для копирования, снимите флажок рядом с именем столбца в прямоугольнике, который представляет таблицу или возвращающий табличное значение объект.</span><span class="sxs-lookup"><span data-stu-id="ddac4-149">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
8.  <span data-ttu-id="ddac4-150">Чтобы скопировать сводные данные, укажите параметры Group By.</span><span class="sxs-lookup"><span data-stu-id="ddac4-150">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="ddac4-151">Дополнительные сведения см. в разделе [Резюмирование результатов запросов (визуальные инструменты для баз данных)](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ddac4-151">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="ddac4-152">При выполнении запроса "вставка результатов" панель [Результаты](results-pane-visual-database-tools.md)не отображает никаких сообщений.</span><span class="sxs-lookup"><span data-stu-id="ddac4-152">When you execute an Insert Results query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="ddac4-153">Вместо этого появляется сообщение о количестве скопированных строк.</span><span class="sxs-lookup"><span data-stu-id="ddac4-153">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddac4-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddac4-154">See Also</span></span>  
 <span data-ttu-id="ddac4-155">[Типы запросов &#40;визуальных инструментов для баз данных&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ddac4-155">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ddac4-156">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="ddac4-156">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
