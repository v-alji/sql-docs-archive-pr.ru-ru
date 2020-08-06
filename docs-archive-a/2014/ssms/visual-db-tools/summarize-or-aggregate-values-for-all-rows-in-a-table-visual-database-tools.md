---
title: Суммировать или агрегировать значения для всех строк в таблице (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- aggregate functions [SQL Server], summarizing query results
ms.assetid: f5af876e-f937-4110-ba09-07999c35a699
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5c4d80c8ab2b811b8e796f0a37b2180a2866c332
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735794"
---
# <a name="summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="1323f-102">Получение суммарных или статистических значений для всех строк в таблице (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="1323f-102">Summarize or Aggregate Values for All Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="1323f-103">Агрегатные функции позволяют вычислять сумму всех значений, содержащихся в таблице.</span><span class="sxs-lookup"><span data-stu-id="1323f-103">Using an aggregate function, you can create a summary for all the values in a table.</span></span> <span data-ttu-id="1323f-104">Например, можно создать запрос наподобие того, что приведен ниже, для отображения общей стоимости всех книг, содержащихся в таблице `titles` :</span><span class="sxs-lookup"><span data-stu-id="1323f-104">For example, you can create a query such as the following to display the total price for all books in the `titles` table:</span></span>  
  
```  
SELECT SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="1323f-105">Один запрос может вычислять сразу несколько статистических выражений, используя агрегатные функции для одного или нескольких столбцов.</span><span class="sxs-lookup"><span data-stu-id="1323f-105">You can create multiple aggregations in the same query by using aggregate functions with more than one column.</span></span> <span data-ttu-id="1323f-106">Например, можно создать запрос, вычисляющий общую сумму по столбцу `price` и среднеарифметическое значение столбца `discount` .</span><span class="sxs-lookup"><span data-stu-id="1323f-106">For example, you can create a query that calculates the total of the `price` column and the average of the `discount` column.</span></span>  
  
 <span data-ttu-id="1323f-107">В одном запросе можно также для одного и того же столбца определять несколько статистических операций (подведение общей суммы, подсчет, усреднение).</span><span class="sxs-lookup"><span data-stu-id="1323f-107">You can also aggregate the same column in different ways (such as totaling, counting, and averaging) in the same query.</span></span> <span data-ttu-id="1323f-108">Например, следующий запрос определяет среднеарифметическое значение и общую сумму столбца `price` в таблице `titles` :</span><span class="sxs-lookup"><span data-stu-id="1323f-108">For example, the following query averages and summarizes the `price` column from the `titles` table:</span></span>  
  
```  
SELECT AVG(price), SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="1323f-109">Если добавить условия поиска, можно вычислять статистические значения на основе подмножества строк, удовлетворяющих заданному условию.</span><span class="sxs-lookup"><span data-stu-id="1323f-109">If you add a search condition, you can aggregate the subset of rows that meet that condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1323f-110">Можно также подсчитать, сколько всего в таблице содержится строк, или строк, удовлетворяющих определенному условию.</span><span class="sxs-lookup"><span data-stu-id="1323f-110">You can also count all the rows in the table or the ones that meet a specific condition.</span></span> <span data-ttu-id="1323f-111">Дополнительные сведения см. в разделе [Подсчет строк в таблице (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1323f-111">For details, see [Count Rows in a Table &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="1323f-112">Если в запросе указано статистическое выражение, то для всех строк в таблице отображается только само это статистическое значение.</span><span class="sxs-lookup"><span data-stu-id="1323f-112">When you create a single aggregation value for all rows in a table, you display only the aggregate values themselves.</span></span> <span data-ttu-id="1323f-113">Например, при подсчете итогового значения столбца `price` в таблице `titles` названия, имена издателей и другие столбцы не отображаются.</span><span class="sxs-lookup"><span data-stu-id="1323f-113">For example, if you are totaling the value of the `price` column of the `titles` table, you would not also display individual titles, publisher names, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1323f-114">При создании подытогов (например, групп) можно выводить значения столбцов для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="1323f-114">If you are subtotaling - that is, creating groups - you can display column values for each group.</span></span> <span data-ttu-id="1323f-115">Дополнительные сведения см. в разделе [Группирование строк в результатах запроса (визуальные инструменты для баз данных)](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1323f-115">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
### <a name="to-aggregate-values-for-all-rows"></a><span data-ttu-id="1323f-116">Статистические выражения по всем строкам</span><span class="sxs-lookup"><span data-stu-id="1323f-116">To aggregate values for all rows</span></span>  
  
1.  <span data-ttu-id="1323f-117">Убедитесь, что таблица, в которой необходимо вычислить статистическую величину, присутствует на панели диаграмм</span><span class="sxs-lookup"><span data-stu-id="1323f-117">Be sure the table you want to aggregate is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="1323f-118">Щелкните правой кнопкой мыши фон панели диаграммы, а затем в контекстном меню выберите пункт **Группировать** .</span><span class="sxs-lookup"><span data-stu-id="1323f-118">Right-click the background of the Diagram pane, then choose **Group By** from the shortcut menu.</span></span> <span data-ttu-id="1323f-119">[Конструктор запросов и представлений](query-and-view-designer-tools-visual-database-tools.md) добавляет столбец **Group By** в сетку на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="1323f-119">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="1323f-120">Добавьте на панель критериев столбец, по которому необходимо вычислить статистическую величину.</span><span class="sxs-lookup"><span data-stu-id="1323f-120">Add the column you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="1323f-121">Убедитесь, что столбец помечен для вывода.</span><span class="sxs-lookup"><span data-stu-id="1323f-121">Be sure that the column is marked for output.</span></span>  
  
     <span data-ttu-id="1323f-122">Конструктор запросов и представлений автоматически назначает суммируемому столбцу псевдоним,</span><span class="sxs-lookup"><span data-stu-id="1323f-122">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="1323f-123">который можно заменить более понятным.</span><span class="sxs-lookup"><span data-stu-id="1323f-123">You can replace this alias with a more meaningful one.</span></span> <span data-ttu-id="1323f-124">Дополнительные сведения см. в разделе [Создание псевдонимов столбцов (визуальные инструменты для баз данных)](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1323f-124">For details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="1323f-125">В столбце сетки **Группировать** выберите нужную агрегатную функцию, например **Sum**, **Avg**, **Min**, **Max**, **Count**.</span><span class="sxs-lookup"><span data-stu-id="1323f-125">In the **Group By** grid column, select the appropriate aggregate function, such as: **Sum**, **Avg**, **Min**, **Max**, **Count**.</span></span> <span data-ttu-id="1323f-126">Если необходимо вычислить статистические значения только для уникальных строк результирующего набора, выберите агрегатную функцию с параметром DISTINCT, например **Min Distinct**.</span><span class="sxs-lookup"><span data-stu-id="1323f-126">If you want to aggregate only unique rows in the result set, choose an aggregate function with the DISTINCT options, such as **Min Distinct**.</span></span> <span data-ttu-id="1323f-127">Не выбирайте параметры **Группировать**, **Выражение**или **Где**, так как они не применяются при статистической обработке всех строк.</span><span class="sxs-lookup"><span data-stu-id="1323f-127">Do not choose **Group By**, **Expression**, or **Where**, because those options do not apply when you are aggregating all rows.</span></span>  
  
     <span data-ttu-id="1323f-128">Конструктор запросов и представлений заменяет указанной агрегатной функцией имя столбца в инструкции, представленной на [панели SQL](sql-pane-visual-database-tools.md) .</span><span class="sxs-lookup"><span data-stu-id="1323f-128">The Query and View Designer replaces the column name in the statement in the [SQL pane](sql-pane-visual-database-tools.md) with the aggregate function that you specify.</span></span> <span data-ttu-id="1323f-129">Например, инструкция SQL может иметь такой вид:</span><span class="sxs-lookup"><span data-stu-id="1323f-129">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT SUM(price)  
    FROM titles  
    ```  
  
5.  <span data-ttu-id="1323f-130">Если необходимо создать в запросе несколько статистических выражений, повторите шаги 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="1323f-130">If you want to create more than one aggregation in the query, repeat steps 3 and 4.</span></span>  
  
     <span data-ttu-id="1323f-131">Если в список выводов запроса или в список сортировки добавляется другой столбец, конструктор запросов и представлений автоматически заполняет термин **Группировать** в столбце сетки **Группировать** .</span><span class="sxs-lookup"><span data-stu-id="1323f-131">When you add another column to the query output list or order by list, the Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span> <span data-ttu-id="1323f-132">Выберите соответствующую агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="1323f-132">Select the appropriate aggregate function.</span></span>  
  
6.  <span data-ttu-id="1323f-133">Если необходимо, добавьте условия поиска для задания подмножества строк, для которых вычисляется сумма.</span><span class="sxs-lookup"><span data-stu-id="1323f-133">Add search conditions, if any, to specify the subset of rows you want to summarize.</span></span>  
  
 <span data-ttu-id="1323f-134">При выполнении запроса на панели результатов отображаются указанные статистические выражения.</span><span class="sxs-lookup"><span data-stu-id="1323f-134">When you execute the query, the Results pane displays the aggregations that you specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1323f-135">Конструктор запросов и представлений обслуживает агрегатные функции в инструкции, отображаемой на панели SQL до тех пор, пока режим «Группировать по» явно не будет выключен.</span><span class="sxs-lookup"><span data-stu-id="1323f-135">The Query and View Designer maintains aggregate functions as part of the SQL statement in the SQL pane until you explicitly turn off Group By mode.</span></span> <span data-ttu-id="1323f-136">Поэтому при изменении типа запроса или изменении состава таблиц и возвращающих табличное значение объектов, присутствующих на панелях диаграмм, конечный запрос может содержать недопустимые агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="1323f-136">Therefore, if you modify your query by changing its type or by changing which tables or table-valued objects are present in the Diagram pane, the resulting query might include invalid aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1323f-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="1323f-137">See Also</span></span>  
 <span data-ttu-id="1323f-138">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1323f-138">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1323f-139">Резюмирование результатов запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="1323f-139">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
