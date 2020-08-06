---
title: Создание запросов с помощью чего-либо, кроме таблицы (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- user-defined functions [SQL Server], queries
- queries [SQL Server], creating
ms.assetid: 8e4a1f0a-8a42-4733-be8d-e21d6dbddb33
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0444c20fe10080949930f23623d5699f7fd3712c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654714"
---
# <a name="create-queries-using-something-besides-a-table-visual-database-tools"></a><span data-ttu-id="d31fa-102">Создание запросов, использующих не только таблицу (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d31fa-102">Create Queries using Something Besides a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="d31fa-103">При написании запроса разработчик указывает, какие требуются столбцы, как отбираются строки и откуда обработчик запросов получает исходные данные.</span><span class="sxs-lookup"><span data-stu-id="d31fa-103">Whenever you write a retrieval query, you articulate what columns you want, what rows you want, and where the query processor should find the original data.</span></span> <span data-ttu-id="d31fa-104">Обычно исходные данные поступают из таблицы или нескольких таблиц, участвующих в соединении.</span><span class="sxs-lookup"><span data-stu-id="d31fa-104">Typically, this original data consists of a table or several tables joined together.</span></span> <span data-ttu-id="d31fa-105">Однако исходные данные могут поступать не только из таблиц.</span><span class="sxs-lookup"><span data-stu-id="d31fa-105">But the original data can come from sources other than tables.</span></span> <span data-ttu-id="d31fa-106">Источниками данных могут служить представления, запросы, синонимы или определяемые пользователем функции, которые возвращают таблицу.</span><span class="sxs-lookup"><span data-stu-id="d31fa-106">In fact, it can come from views, queries, synonyms, or user-defined functions that return a table.</span></span>  
  
## <a name="using-a-view-in-place-of-a-table"></a><span data-ttu-id="d31fa-107">Использование представления вместо таблицы</span><span class="sxs-lookup"><span data-stu-id="d31fa-107">Using a View in Place of a Table</span></span>  
 <span data-ttu-id="d31fa-108">Допускается выбор строк из представления.</span><span class="sxs-lookup"><span data-stu-id="d31fa-108">You can select rows from a view.</span></span> <span data-ttu-id="d31fa-109">Например, предположим, что база данных содержит представление с именем «ExpensiveBooks», строки в котором описывают книги с ценой, превышающей 19,99.</span><span class="sxs-lookup"><span data-stu-id="d31fa-109">For example, suppose the database includes a view called "ExpensiveBooks," in which each row describes a title whose price exceeds 19.99.</span></span> <span data-ttu-id="d31fa-110">Определение представления может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d31fa-110">The view definition might look like this:</span></span>  
  
```  
SELECT *  
FROM titles  
WHERE price > 19.99  
  
```  
  
 <span data-ttu-id="d31fa-111">Можно отобрать дорогие книги по психологии, выбирая их из представления ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="d31fa-111">You can select the expensive psychology books merely by selecting the psychology books from the ExpensiveBooks view.</span></span> <span data-ttu-id="d31fa-112">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d31fa-112">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM ExpensiveBooks  
WHERE type = 'psychology'  
  
```  
  
 <span data-ttu-id="d31fa-113">Допускается включение представления в операцию JOIN.</span><span class="sxs-lookup"><span data-stu-id="d31fa-113">Similarly, a view can participate in a JOIN operation.</span></span> <span data-ttu-id="d31fa-114">Например, можно получить данные по продажам дорогих книг, соединив таблицу продаж с представлением ExpensiveBooks.</span><span class="sxs-lookup"><span data-stu-id="d31fa-114">For example, you can find the sales of expensive books merely by joining the sales table to the ExpensiveBooks view.</span></span> <span data-ttu-id="d31fa-115">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d31fa-115">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *  
FROM sales   
         INNER JOIN   
         ExpensiveBooks   
         ON sales.title_id   
         =  ExpensiveBooks.title_id  
  
```  
  
 <span data-ttu-id="d31fa-116">Дополнительные сведения о добавлении представления в запрос см. в разделе [Добавление таблиц в запросы (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d31fa-116">For more information about adding a view to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-query-in-place-of-a-table"></a><span data-ttu-id="d31fa-117">Использование запроса вместо таблицы</span><span class="sxs-lookup"><span data-stu-id="d31fa-117">Using a Query in Place of a Table</span></span>  
 <span data-ttu-id="d31fa-118">Допускается выбор строк из запроса.</span><span class="sxs-lookup"><span data-stu-id="d31fa-118">You can select rows from a query.</span></span> <span data-ttu-id="d31fa-119">Предположим, что имеется запрос, возвращающий названия и идентификаторы для книг, написанных соавторами, т. е. имеющих более одного автора.</span><span class="sxs-lookup"><span data-stu-id="d31fa-119">For example, suppose you have already written a query retrieving titles and identifiers of the coauthored books - the books with more than one author.</span></span> <span data-ttu-id="d31fa-120">Код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d31fa-120">The SQL might look like this:</span></span>  
  
```  
SELECT   
     titles.title_id, title, type  
FROM   
     titleauthor   
         INNER JOIN  
         titles   
         ON titleauthor.title_id   
         =  titles.title_id   
GROUP BY   
     titles.title_id, title, type  
HAVING COUNT(*) > 1  
  
```  
  
 <span data-ttu-id="d31fa-121">После этого можно написать другой запрос, использующий этот результат.</span><span class="sxs-lookup"><span data-stu-id="d31fa-121">You can then write another query that builds on this result.</span></span> <span data-ttu-id="d31fa-122">Например, запрос, возвращающий книги по психологии, написанные соавторами,</span><span class="sxs-lookup"><span data-stu-id="d31fa-122">For example, you can write a query that retrieves the coauthored psychology books.</span></span> <span data-ttu-id="d31fa-123">будет использовать существующий запрос как источник данных.</span><span class="sxs-lookup"><span data-stu-id="d31fa-123">To write this new query, you can use the existing query as the source of the new query's data.</span></span> <span data-ttu-id="d31fa-124">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d31fa-124">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    title  
FROM   
    (  
    SELECT   
        titles.title_id,   
        title,   
        type  
    FROM   
        titleauthor   
            INNER JOIN  
            titles   
            ON titleauthor.title_id   
            =  titles.title_id   
    GROUP BY   
        titles.title_id,   
        title,   
        type  
    HAVING COUNT(*) > 1  
    )   
    co_authored_books  
WHERE     type = 'psychology'  
  
```  
  
 <span data-ttu-id="d31fa-125">Полужирным шрифтом выделен существующий запрос, используемый как источник данных нового запроса.</span><span class="sxs-lookup"><span data-stu-id="d31fa-125">The emphasized text shows the existing query used as the source of the new query's data.</span></span> <span data-ttu-id="d31fa-126">Следует отметить, что в новом запросе для существующего запроса используется псевдоним (co_authored_books).</span><span class="sxs-lookup"><span data-stu-id="d31fa-126">Note that the new query uses an alias ("co_authored_books") for the existing query.</span></span> <span data-ttu-id="d31fa-127">Дополнительные сведения о псевдонимах см. в разделах [Создание псевдонимов таблицы (визуальные инструменты для баз данных)](create-table-aliases-visual-database-tools.md) и [Создание псевдонимов столбцов (визуальные инструменты для баз данных)](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d31fa-127">For more information about aliases, see [Create Table Aliases &#40;Visual Database Tools&#41;](create-table-aliases-visual-database-tools.md) and [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="d31fa-128">Допускается включение запроса в операцию JOIN.</span><span class="sxs-lookup"><span data-stu-id="d31fa-128">Similarly, a query can participate in a JOIN operation.</span></span> <span data-ttu-id="d31fa-129">Например, можно получить данные по продажам дорогих книг, написанных соавторами, соединив представление ExpensiveBooks с существующим запросом.</span><span class="sxs-lookup"><span data-stu-id="d31fa-129">For example, you can find the sales of expensive coauthored books merely by joining the ExpensiveBooks view to the query retrieving the coauthored books.</span></span> <span data-ttu-id="d31fa-130">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d31fa-130">The resulting SQL might look like this:</span></span>  
  
```  
SELECT   
    ExpensiveBooks.title  
FROM   
    ExpensiveBooks   
        INNER JOIN  
        (  
        SELECT   
            titles.title_id,   
            title,   
            type  
        FROM   
            titleauthor   
                INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
        GROUP BY   
            titles.title_id,   
            title,   
            type  
        HAVING COUNT(*) > 1  
        )  
```  
  
 <span data-ttu-id="d31fa-131">Дополнительные сведения о добавлении запроса в запрос см. в разделе [Добавление таблиц в запросы (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d31fa-131">For more information about adding a query to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="using-a-user-defined-function-in-place-of-a-table"></a><span data-ttu-id="d31fa-132">Использование определяемых пользователем функций вместо таблицы</span><span class="sxs-lookup"><span data-stu-id="d31fa-132">Using a User-Defined Function in Place of a Table</span></span>  
 <span data-ttu-id="d31fa-133">В SQL Server 2000 или более поздних версиях поддерживается создание определяемой пользователем функции, возвращающей таблицу.</span><span class="sxs-lookup"><span data-stu-id="d31fa-133">In SQL Server 2000 or higher, you can create a user-defined function that returns a table.</span></span> <span data-ttu-id="d31fa-134">Такие функции полезны при использовании сложной или процедурной логики.</span><span class="sxs-lookup"><span data-stu-id="d31fa-134">Such functions are useful for performing complex or procedural logic.</span></span>  
  
 <span data-ttu-id="d31fa-135">Предположим, что таблица сотрудников содержит дополнительный столбец employee.manager_emp_id и что существует внешний ключ от столбца manager_emp_id к столбцу employee.emp_id.</span><span class="sxs-lookup"><span data-stu-id="d31fa-135">For example, suppose the employee table contains an additional column, employee.manager_emp_id, and that a foreign key exists from manager_emp_id to employee.emp_id.</span></span> <span data-ttu-id="d31fa-136">В каждой строке таблицы сотрудников столбец manager_emp_id указывает начальника конкретного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="d31fa-136">Within each row of the employee table, the manager_emp_id column indicates the employee's boss.</span></span> <span data-ttu-id="d31fa-137">Точнее, указывается код emp_id начальника конкретного сотрудника.</span><span class="sxs-lookup"><span data-stu-id="d31fa-137">More precisely, it indicates the employee's boss's emp_id.</span></span> <span data-ttu-id="d31fa-138">Можно создать определяемую пользователем функцию, которая возвращает таблицу, содержащую одну строку для каждого сотрудника, работающего в иерархии подчиненности для руководителя высшего уровня.</span><span class="sxs-lookup"><span data-stu-id="d31fa-138">You can create a user-defined function that returns a table containing one row for each employee working within a particular high-level manager's organizational hierarchy.</span></span> <span data-ttu-id="d31fa-139">Функцию можно назвать fn_GetWholeTeam и определить так, чтобы входной переменной был идентификатор руководителя, сведения о подчиненных которого требуется получить.</span><span class="sxs-lookup"><span data-stu-id="d31fa-139">You might call the function fn_GetWholeTeam, and design it to take an input variable - the emp_id of the manager whose team you want to retrieve.</span></span>  
  
 <span data-ttu-id="d31fa-140">Затем можно написать запрос, использующий функцию fn_GetWholeTeam как источник данных.</span><span class="sxs-lookup"><span data-stu-id="d31fa-140">You can write a query that uses the fn_GetWholeTeam function as a source of data.</span></span> <span data-ttu-id="d31fa-141">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d31fa-141">The resulting SQL might look like this:</span></span>  
  
```  
SELECT *   
FROM   
     fn_GetWholeTeam ('VPA30890F')  
  
```  
  
 <span data-ttu-id="d31fa-142">«VPA30890F» представляет код emp_id руководителя, сведения о подчиненных которого требуется получить.</span><span class="sxs-lookup"><span data-stu-id="d31fa-142">"VPA30890F" is the emp_id of the manager whose organization you want to retrieve.</span></span> <span data-ttu-id="d31fa-143">Дополнительные сведения о добавлении пользовательской функции в запрос см. в разделе [Добавление таблиц в запросы (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d31fa-143">For more information about adding a user-defined function to a query, see [Add Tables to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="d31fa-144">Подробное описание определяемых пользователем функций см. в разделе [Определяемые пользователем функции](../../relational-databases/user-defined-functions/user-defined-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d31fa-144">For a complete description of user-defined functions, see [User-Defined Functions](../../relational-databases/user-defined-functions/user-defined-functions.md).</span></span>  
  
  
