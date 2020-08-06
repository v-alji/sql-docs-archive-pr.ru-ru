---
title: Использование предложений HAVING и WHERE в одном запросе (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- search conditions [SQL Server], HAVING clause
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- HAVING clause, search criteria
- search conditions [SQL Server], WHERE clause
- WHERE clause, search criteria
- excluding rows
ms.assetid: 1e07cf56-b4b7-4c49-8ddd-c276812a7148
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f6b471a60bf225ee61bdbbf0ecec30f21a92cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729006"
---
# <a name="use-having-and-where-clauses-in-the-same-query-visual-database-tools"></a><span data-ttu-id="683e9-102">Использование предложения HAVING и WHERE в одном запросе (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="683e9-102">Use HAVING and WHERE Clauses in the Same Query (Visual Database Tools)</span></span>
  <span data-ttu-id="683e9-103">В некоторых экземплярах может понадобиться исключить отдельные строки из групп (с использованием предложения WHERE) до того, как применять условие к группе как к целому (с использованием предложения HAVING).</span><span class="sxs-lookup"><span data-stu-id="683e9-103">In some instances, you might want to exclude individual rows from groups (using a WHERE clause) before applying a condition to groups as a whole (using a HAVING clause).</span></span>  
  
 <span data-ttu-id="683e9-104">Предложение HAVING подобно предложению WHERE, но применимо только к целым группам (то есть к строкам в результирующем наборе, представляющим собой группы), тогда как предложение WHERE применимо к отдельным строкам.</span><span class="sxs-lookup"><span data-stu-id="683e9-104">A HAVING clause is like a WHERE clause, but applies only to groups as a whole (that is, to the rows in the result set representing groups), whereas the WHERE clause applies to individual rows.</span></span> <span data-ttu-id="683e9-105">В запросе могут содержаться оба предложения: WHERE и HAVING.</span><span class="sxs-lookup"><span data-stu-id="683e9-105">A query can contain both a WHERE clause and a HAVING clause.</span></span> <span data-ttu-id="683e9-106">В этом случае:</span><span class="sxs-lookup"><span data-stu-id="683e9-106">In that case:</span></span>  
  
-   <span data-ttu-id="683e9-107">Предложение WHERE применяется сначала к отдельным строкам таблиц или возвращающих табличное значение объектов на панели диаграмм.</span><span class="sxs-lookup"><span data-stu-id="683e9-107">The WHERE clause is applied first to the individual rows in the tables or table-valued objects in the Diagram pane.</span></span> <span data-ttu-id="683e9-108">Группируются только строки, которые удовлетворяют условиям в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="683e9-108">Only the rows that meet the conditions in the WHERE clause are grouped.</span></span>  
  
-   <span data-ttu-id="683e9-109">Затем предложение HAVING применяется к строкам в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="683e9-109">The HAVING clause is then applied to the rows in the result set.</span></span> <span data-ttu-id="683e9-110">Только строки, которые удовлетворяют условиям HAVING, появляются в результирующем запросе.</span><span class="sxs-lookup"><span data-stu-id="683e9-110">Only the groups that meet the HAVING conditions appear in the query output.</span></span> <span data-ttu-id="683e9-111">Можно применить предложение HAVING только к тем столбцам, которые появляются в предложении GROUP BY или агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="683e9-111">You can apply a HAVING clause only to columns that also appear in the GROUP BY clause or in an aggregate function.</span></span>  
  
 <span data-ttu-id="683e9-112">Например, соединяются таблицы `titles` и `publishers` для создания запроса, в котором показана средняя цена книги для группы издателей.</span><span class="sxs-lookup"><span data-stu-id="683e9-112">For example, imagine that you are joining the `titles` and `publishers` tables to create a query showing the average book price for a set of publishers.</span></span> <span data-ttu-id="683e9-113">Требуется средняя цена книги только определенной группы издателей — например, только издателей в штате Калифорния.</span><span class="sxs-lookup"><span data-stu-id="683e9-113">You want to see the average price for only a specific set of publishers - perhaps only the publishers in the state of California.</span></span> <span data-ttu-id="683e9-114">При этом нужно показать только те средние цены, которые превышают $10,00.</span><span class="sxs-lookup"><span data-stu-id="683e9-114">And even then, you want to see the average price only if it is over $10.00.</span></span>  
  
 <span data-ttu-id="683e9-115">Первое условие можно задать с помощью предложения WHERE, которое устраняет всех издателей не из Калифорнии перед тем, как начать вычисление средней цены.</span><span class="sxs-lookup"><span data-stu-id="683e9-115">You can establish the first condition by including a WHERE clause, which discards any publishers that are not in California, before calculating average prices.</span></span> <span data-ttu-id="683e9-116">Второе условие требует предложения HAVING, так как условие основано на результатах группирования и сводных данных.</span><span class="sxs-lookup"><span data-stu-id="683e9-116">The second condition requires a HAVING clause, because the condition is based on the results of grouping and summarizing the data.</span></span> <span data-ttu-id="683e9-117">Конечная инструкция SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="683e9-117">The resulting SQL statement might look like this:</span></span>  
  
```  
SELECT titles.pub_id, AVG(titles.price)  
FROM titles INNER JOIN publishers  
   ON titles.pub_id = publishers.pub_id  
WHERE publishers.state = 'CA'  
GROUP BY titles.pub_id  
HAVING AVG(price) > 10  
```  
  
 <span data-ttu-id="683e9-118">Можно создать оба предложения HAVING и WHERE на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="683e9-118">You can create both HAVING and WHERE clauses in the Criteria pane.</span></span> <span data-ttu-id="683e9-119">По умолчанию любое заданное условие поиска для столбца становится частью предложения HAVING.</span><span class="sxs-lookup"><span data-stu-id="683e9-119">By default, if you specify a search condition for a column, the condition becomes part of the HAVING clause.</span></span> <span data-ttu-id="683e9-120">Однако можно изменить условие, сделав его предложением WHERE.</span><span class="sxs-lookup"><span data-stu-id="683e9-120">However, you can change the condition to be a WHERE clause.</span></span>  
  
 <span data-ttu-id="683e9-121">Можно создать предложение WHERE и HAVING для одного и того же столбца.</span><span class="sxs-lookup"><span data-stu-id="683e9-121">You can create a WHERE clause and HAVING clause involving the same column.</span></span> <span data-ttu-id="683e9-122">Для этого необходимо дважды добавить столбец на панели критериев, затем указать один экземпляр как часть предложения HAVING и другой экземпляр как часть предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="683e9-122">To do so, you must add the column twice to the Criteria pane, then specify one instance as part of the HAVING clause and the other instance as part of the WHERE clause.</span></span>  
  
### <a name="to-specify-a-where-condition-in-an-aggregate-query"></a><span data-ttu-id="683e9-123">Задание условия WHERE в статистическом запросе</span><span class="sxs-lookup"><span data-stu-id="683e9-123">To specify a WHERE condition in an aggregate query</span></span>  
  
1.  <span data-ttu-id="683e9-124">Укажите группы для запроса.</span><span class="sxs-lookup"><span data-stu-id="683e9-124">Specify the groups for your query.</span></span> <span data-ttu-id="683e9-125">Дополнительные сведения см. в разделе [Группирование строк в результатах запроса (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="683e9-125">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="683e9-126">Если столбец, на котором основывается условие WHERE, находится не на панели критериев, то добавьте его на панель критериев.</span><span class="sxs-lookup"><span data-stu-id="683e9-126">If it is not already in the Criteria pane, add the column on which you want to base the WHERE condition.</span></span>  
  
3.  <span data-ttu-id="683e9-127">Очистите столбец **Вывод** , если столбец данных не является частью предложения GROUP BY или не входит в агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="683e9-127">Clear the **Output** column unless the data column is part of the GROUP BY clause or included in an aggregate function.</span></span>  
  
4.  <span data-ttu-id="683e9-128">В столбце **Фильтр** укажите условие WHERE.</span><span class="sxs-lookup"><span data-stu-id="683e9-128">In the **Filter** column, specify the WHERE condition.</span></span> <span data-ttu-id="683e9-129">Конструктор запросов и представлений добавляет условие в предложение HAVING инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="683e9-129">The Query and View Designer adds the condition to the HAVING clause of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="683e9-130">В качестве примера данной процедуры показан запрос, соединяющий две таблицы `titles` и `publishers`.</span><span class="sxs-lookup"><span data-stu-id="683e9-130">The query shown in the example for this procedure joins two tables, `titles` and `publishers`.</span></span>  
  
     <span data-ttu-id="683e9-131">В этой точке в запросе инструкции SQL содержится предложение HAVING:</span><span class="sxs-lookup"><span data-stu-id="683e9-131">At this point in the query, the SQL statement contains a HAVING clause:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    GROUP BY titles.pub_id  
    HAVING publishers.state = 'CA'  
    ```  
  
5.  <span data-ttu-id="683e9-132">В столбце **Группировать** выберите **Where** из списка параметров группировки и сводки.</span><span class="sxs-lookup"><span data-stu-id="683e9-132">In the **Group By** column, select **Where** from the list of group and summary options.</span></span> <span data-ttu-id="683e9-133">Конструктор запросов и представлений удаляет условие из предложения HAVING инструкции SQL и добавляет его в предложение WHERE.</span><span class="sxs-lookup"><span data-stu-id="683e9-133">The Query and View Designer removes the condition from the HAVING clause in the SQL statement and adds it to the WHERE clause.</span></span>  
  
     <span data-ttu-id="683e9-134">Инструкция SQL изменяется, теперь она содержит предложение WHERE:</span><span class="sxs-lookup"><span data-stu-id="683e9-134">The SQL statement changes to include a WHERE clause instead:</span></span>  
  
    ```  
    SELECT titles.pub_id, AVG(titles.price)  
    FROM titles INNER JOIN publishers   
       ON titles.pub_id = publishers.pub_id  
    WHERE publishers.state = 'CA'  
    GROUP BY titles.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="683e9-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="683e9-135">See Also</span></span>  
 <span data-ttu-id="683e9-136">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="683e9-136">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="683e9-137">Резюмирование результатов запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="683e9-137">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
