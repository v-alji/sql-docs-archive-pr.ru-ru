---
title: Группировка строк в результатах запросов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing table subsets
- grouping rows
- grouping query results
ms.assetid: b07082d5-4d55-4903-9af9-4c470554c6d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52de25c86425d95f5917d89c8a3f4fec8939fb16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665200"
---
# <a name="group-rows-in-query-results-visual-database-tools"></a><span data-ttu-id="7068c-102">Группирование строк в результатах запроса (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7068c-102">Group Rows in Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="7068c-103">Если нужно создать подытог или отобразить другие сводные сведения о подмножествах таблицы, создайте группы, используя статистический запрос.</span><span class="sxs-lookup"><span data-stu-id="7068c-103">If you want to create subtotals or show other summary information for subsets of a table, you create groups using an aggregate query.</span></span> <span data-ttu-id="7068c-104">Каждая такая группа обобщает данные всех строк таблицы, имеющих одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="7068c-104">Each group summarizes the data for all the rows in the table that have the same value.</span></span>  
  
 <span data-ttu-id="7068c-105">Например, нужно узнать среднюю стоимость книг, данные о которых хранятся в таблице `titles` , и разделить результаты в соответствии с идентификаторами издателей.</span><span class="sxs-lookup"><span data-stu-id="7068c-105">For example, you might want to see the average price of a book in the `titles` table, but break the results down by publisher.</span></span> <span data-ttu-id="7068c-106">Для этого следует сгруппировать запрос на основе идентификатора издателя (например `pub_id`).</span><span class="sxs-lookup"><span data-stu-id="7068c-106">To do so, you group the query by publisher (for example, `pub_id`).</span></span> <span data-ttu-id="7068c-107">Сведения, выведенные таким запросом, могли бы выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7068c-107">The resulting query output might look like this:</span></span>  
  
 <span data-ttu-id="7068c-108">![Результаты запроса: средние цены, сгруппированные по издателям](../../database-engine/media//dv3w9e1.gif "Результаты запроса: средние цены, сгруппированные по издателям")</span><span class="sxs-lookup"><span data-stu-id="7068c-108">![Query results: average price grouped by publisher](../../database-engine/media//dv3w9e1.gif "Query results: average price grouped by publisher")</span></span>  
  
 <span data-ttu-id="7068c-109">Группируя данные, можно отобразить только сводные или сгруппированные данные, подобные следующим.</span><span class="sxs-lookup"><span data-stu-id="7068c-109">When you group data, you can display only summary or grouped data, such as:</span></span>  
  
-   <span data-ttu-id="7068c-110">Значения сгруппированных столбцов (столбцов, указанных в предложении GROUP BY).</span><span class="sxs-lookup"><span data-stu-id="7068c-110">The values of the grouped columns (those that appear in the GROUP BY clause).</span></span> <span data-ttu-id="7068c-111">В приведенном выше примере столбец `pub_id` является сгруппированным.</span><span class="sxs-lookup"><span data-stu-id="7068c-111">In the example above, `pub_id` is the grouped column.</span></span>  
  
-   <span data-ttu-id="7068c-112">Значения, созданные агрегатными функциями, такими как SUM( ) и AVG( ).</span><span class="sxs-lookup"><span data-stu-id="7068c-112">Values produced by aggregate functions such as SUM( ) and AVG( ).</span></span> <span data-ttu-id="7068c-113">В приведенном выше примере второй столбец создается путем применения функции AVG( ) к столбцу `price` .</span><span class="sxs-lookup"><span data-stu-id="7068c-113">In the example above, the second column is produced by using the AVG( ) function with the `price` column.</span></span>  
  
 <span data-ttu-id="7068c-114">Отобразить значения отдельных строк нельзя.</span><span class="sxs-lookup"><span data-stu-id="7068c-114">You cannot display values from individual rows.</span></span> <span data-ttu-id="7068c-115">Например, если группируются данные только по идентификаторам издателей, нельзя отобразить в запросе еще и отдельные названия книг.</span><span class="sxs-lookup"><span data-stu-id="7068c-115">For example, if you group only by publisher, you cannot also display individual titles in the query.</span></span> <span data-ttu-id="7068c-116">Таким образом, если столбцы добавляются в вывод запроса, [конструктор запросов и представлений](visual-database-tools.md) автоматически добавляет их в предложение GROUP BY инструкции на [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7068c-116">Therefore, if you add columns to the query output, the [Query and View Designer](visual-database-tools.md) automatically adds them to the GROUP BY clause of the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="7068c-117">Если нужно, чтобы столбец содержал статистические данные, можете определить для него агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="7068c-117">If you want a column to be aggregated instead, you can specify an aggregate function for that column.</span></span>  
  
 <span data-ttu-id="7068c-118">Если данные группируются по нескольким столбцам, каждая группа в запросе отображает статистические значения всех столбцов группировки.</span><span class="sxs-lookup"><span data-stu-id="7068c-118">If you group by more than one column, each group in the query shows the aggregate values for all grouping columns.</span></span>  
  
 <span data-ttu-id="7068c-119">Например, следующий запрос таблицы `titles` группирует данные по идентификаторам издателей (`pub_id`) и типам книг (`type`).</span><span class="sxs-lookup"><span data-stu-id="7068c-119">For example, the following query against the `titles` table groups by publisher (`pub_id`) and also by book type (`type`).</span></span> <span data-ttu-id="7068c-120">Результаты запроса упорядочиваются по идентификаторам издателей и представляют сводные данные о каждом типе книг, издаваемых издателем:</span><span class="sxs-lookup"><span data-stu-id="7068c-120">The query results are ordered by publisher and show summary information for each different type of book that the publisher produces:</span></span>  
  
```  
SELECT pub_id, type, SUM(price) Total_price  
FROM titles  
GROUP BY pub_id, type  
```  
  
 <span data-ttu-id="7068c-121">Итоговый вывод мог бы выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7068c-121">The resulting output might look like this:</span></span>  
  
 <span data-ttu-id="7068c-122">![Результаты запроса: цены, сгруппированные по издателям и типам](../../database-engine/media//dv3w9e2.gif "Результаты запроса: цены, сгруппированные по издателям и типам")</span><span class="sxs-lookup"><span data-stu-id="7068c-122">![Query results: price grouped by publisher and type](../../database-engine/media//dv3w9e2.gif "Query results: price grouped by publisher and type")</span></span>  
  
### <a name="to-group-rows"></a><span data-ttu-id="7068c-123">Группирование строк</span><span class="sxs-lookup"><span data-stu-id="7068c-123">To group rows</span></span>  
  
1.  <span data-ttu-id="7068c-124">Инициируйте запрос, добавив таблицы, сводную информацию о которых нужно получить, на панель диаграмм.</span><span class="sxs-lookup"><span data-stu-id="7068c-124">Start the query by adding the tables you want to summarize to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="7068c-125">Щелкните правой кнопкой мыши фон панели диаграммы и выберите из контекстного меню пункт **Добавить Group By** .</span><span class="sxs-lookup"><span data-stu-id="7068c-125">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="7068c-126">Конструктор запросов и представлений добавляет столбец **Группировать** в сетку на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="7068c-126">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="7068c-127">Добавьте столбец или столбцы, которые нужно сгруппировать, на панель критериев.</span><span class="sxs-lookup"><span data-stu-id="7068c-127">Add the column or columns you want to group to the Criteria pane.</span></span> <span data-ttu-id="7068c-128">Если нужно, чтобы столбец был отображен в выводе запроса, не забудьте убедиться в том, что для вывода выбран столбец **Вывод** .</span><span class="sxs-lookup"><span data-stu-id="7068c-128">If you want the column to appear in the query output, be sure that the **Output** column is selected for output.</span></span>  
  
     <span data-ttu-id="7068c-129">Конструктор запросов и представлений добавит в инструкцию, отображаемую на панели SQL, предложение GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="7068c-129">The Query and View Designer adds a GROUP BY clause to the statement in the SQL pane.</span></span> <span data-ttu-id="7068c-130">Например, инструкция SQL может иметь такой вид:</span><span class="sxs-lookup"><span data-stu-id="7068c-130">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT pub_id  
    FROM titles  
    GROUP BY pub_id  
    ```  
  
4.  <span data-ttu-id="7068c-131">Добавьте на панель критериев столбец или столбцы, статистическую информацию о которых нужно получить.</span><span class="sxs-lookup"><span data-stu-id="7068c-131">Add the column or columns you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="7068c-132">Убедитесь, что столбец помечен для вывода.</span><span class="sxs-lookup"><span data-stu-id="7068c-132">Be sure that the column is marked for output.</span></span>  
  
5.  <span data-ttu-id="7068c-133">В ячейке **Группировать** для столбца, статистическую информацию о котором нужно получить, выберите подходящую агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="7068c-133">In the **Group By** grid cell for the column that is going to be aggregated, select the appropriate aggregate function.</span></span>  
  
     <span data-ttu-id="7068c-134">Конструктор запросов и представлений автоматически назначает суммируемому столбцу псевдоним,</span><span class="sxs-lookup"><span data-stu-id="7068c-134">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="7068c-135">Псевдоним, созданный автоматически, можно заменить более содержательным псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="7068c-135">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="7068c-136">Дополнительные сведения см. в разделе [Создание псевдонимов столбцов (визуальные инструменты для баз данных)](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7068c-136">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="7068c-137">![Добавление псевдонима столбца в результирующий набор запроса](../../database-engine/media//dv3w9e3.gif "Добавление псевдонима столбца в результирующий набор запроса")</span><span class="sxs-lookup"><span data-stu-id="7068c-137">![Adding a column alias to the query result set](../../database-engine/media//dv3w9e3.gif "Adding a column alias to the query result set")</span></span>  
  
     <span data-ttu-id="7068c-138">Соответствующая инструкция могла бы выглядеть на панели **SQL** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7068c-138">The corresponding statement in the **SQL** pane might look like this:</span></span>  
  
    ```  
    SELECT   pub_id, SUM(price) AS Totalprice  
    FROM     titles  
    GROUP BY pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7068c-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="7068c-139">See Also</span></span>  
 [<span data-ttu-id="7068c-140">Результаты запросов сортировки и группирования (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7068c-140">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
