---
title: Сортировка строк (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- sorting rows [SQL Server]
- sorting query results [SQL Server]
ms.assetid: 780ef467-f96e-4373-8235-6dacbedb05a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4939c08a4be8c6a7aa3a52d55928abe077f25d76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737367"
---
# <a name="sort-rows-visual-database-tools"></a><span data-ttu-id="d3f40-102">Сортировка строк (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d3f40-102">Sort Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="d3f40-103">Строки в результатах запроса можно сортировать.</span><span class="sxs-lookup"><span data-stu-id="d3f40-103">You can order the rows in a query result.</span></span> <span data-ttu-id="d3f40-104">То есть можно указать конкретный столбец или набор столбцов, значениями которых определяется порядок строк в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="d3f40-104">That is, you can name a particular column or set of columns whose values determine the order of rows in the result set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3f40-105">Порядок сортировки частично определяется параметрами сортировки столбца.</span><span class="sxs-lookup"><span data-stu-id="d3f40-105">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="d3f40-106">Очередность использования параметров сортировки можно изменить в диалоговом окне [Параметры сортировки](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d3f40-106">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="d3f40-107">Существует несколько способов сортировки результатов запроса:</span><span class="sxs-lookup"><span data-stu-id="d3f40-107">There are several ways in which you can sort query results:</span></span>  
  
-   <span data-ttu-id="d3f40-108">**Можно упорядочивать строки по возрастанию или по убыванию.** По умолчанию SQL использует столбцы, по которым ведется упорядочение, для расположения строк в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="d3f40-108">**You can arrange rows in ascending or descending order** By default, SQL uses order-by columns to arrange rows in ascending order.</span></span> <span data-ttu-id="d3f40-109">Например, чтобы упорядочить наименования книг в порядке возрастания цен, достаточно отсортировать строки по столбцу цен.</span><span class="sxs-lookup"><span data-stu-id="d3f40-109">For example, to arrange the book titles by ascending price, simply sort the rows by the price column.</span></span> <span data-ttu-id="d3f40-110">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3f40-110">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price  
  
    ```  
  
     <span data-ttu-id="d3f40-111">С другой стороны, если нужно сортировать названия книг так, чтобы в начале списка были расположены самые дорогие, можно явно указать порядок, в котором первым располагается элемент с самым высоким значением.</span><span class="sxs-lookup"><span data-stu-id="d3f40-111">On the other hand, if you want to arrange the titles with the more expensive books first, you can explicitly specify a highest-first ordering.</span></span> <span data-ttu-id="d3f40-112">То есть указать, что строки результата должны быть упорядочены по убыванию значений в столбце цен.</span><span class="sxs-lookup"><span data-stu-id="d3f40-112">That is, you indicate that the result rows should be arranged by descending values of the price column.</span></span> <span data-ttu-id="d3f40-113">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3f40-113">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="d3f40-114">**Можно сортировать по нескольким столбцам.** Например, можно создать результирующий набор, содержащий по одной строке для каждого автора, упорядоченный сначала по штату, затем по городу.</span><span class="sxs-lookup"><span data-stu-id="d3f40-114">**You can sort by multiple columns** For example, you can create a result set with one row for each author, ordering first by state and then by city.</span></span> <span data-ttu-id="d3f40-115">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3f40-115">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM authors   
    ORDER BY state, city  
  
    ```  
  
-   <span data-ttu-id="d3f40-116">**Можно сортировать по столбцам, не отображаемым в наборе результатов.** Например можно создать результирующий набор, в начале которого размещены самые дорогостоящие книги, хотя столбец цен при этом не отображается.</span><span class="sxs-lookup"><span data-stu-id="d3f40-116">**You can sort by columns not appearing in the result set** For example, you can create a result set with the most expensive titles first, even though the prices do not appear.</span></span> <span data-ttu-id="d3f40-117">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3f40-117">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title_id, title  
    FROM titles  
    ORDER BY price DESC  
  
    ```  
  
-   <span data-ttu-id="d3f40-118">**Можно сортировать по производным столбцам.** Например, можно создать результирующий набор, каждая строка которого будет содержать наименование книги, причем первыми будут перечислены книги, авторы которых получают самый большой процент отчислений с проданного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d3f40-118">**You can sort by derived columns** For example, you can create a result set in which each row contains a book title - with the books that pay the highest royalty per copy appearing first.</span></span> <span data-ttu-id="d3f40-119">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3f40-119">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title, price * royalty / 100 as royalty_per_unit  
    FROM titles  
    ORDER BY royalty_per_unit DESC  
  
    ```  
  
     <span data-ttu-id="d3f40-120">(Формула для вычисления авторского гонорара с проданного экземпляра каждой книги выделена.)</span><span class="sxs-lookup"><span data-stu-id="d3f40-120">(The formula for calculating the royalty that each book earns per copy is emphasized.)</span></span>  
  
     <span data-ttu-id="d3f40-121">Чтобы вычислить производный столбец, можно использовать синтаксис SQL, как в предыдущем примере, или определяемую пользователем функцию, которая возвращает скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="d3f40-121">To calculate a derived column, you can use SQL syntax, as in the preceding example, or you can use a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="d3f40-122">Дополнительные сведения об определяемых пользователем функциях см. в документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3f40-122">For more information about user-defined functions, see the SQL Server documentation.</span></span>  
  
-   <span data-ttu-id="d3f40-123">**Можно сортировать сгруппированные строки.** Например, можно создать результирующий набор, каждая строка которого будет описывать какой-либо город и указывать количество авторов из этого города, причем первыми будут перечислены города с большим числом авторов.</span><span class="sxs-lookup"><span data-stu-id="d3f40-123">**You can sort grouped rows** For example; you can create a result set in which each row describes a city, plus the number of authors in that city - with the cities containing many authors appearing first.</span></span> <span data-ttu-id="d3f40-124">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3f40-124">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ORDER BY COUNT(*) DESC, state  
  
    ```  
  
     <span data-ttu-id="d3f40-125">Обратите внимание на то, что в запросе используется `state` в качестве второстепенного столбца сортировки.</span><span class="sxs-lookup"><span data-stu-id="d3f40-125">Notice that the query uses `state` as a secondary sort column.</span></span> <span data-ttu-id="d3f40-126">Таким образом, если в двух штатах имеется одинаковое количество авторов, эти штаты располагаются в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="d3f40-126">Thus, if two states have the same number of authors, those states will appear in alphabetical order.</span></span>  
  
-   <span data-ttu-id="d3f40-127">**Можно сортировать с использованием данных в разных языковых форматах** То есть можно сортировать столбец, используя соглашения о порядке сортировки, отличные от соглашений по умолчанию, применяемых для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="d3f40-127">**You can sort using international data** That is; you can sort a column using collating conventions that differ from the default conventions for that column.</span></span> <span data-ttu-id="d3f40-128">Например, можно написать запрос, получающий все заголовки книг с помощью Джэйми пати?? вывода.</span><span class="sxs-lookup"><span data-stu-id="d3f40-128">For example, you can write a query that retrieves all the book titles by Jaime Pati??o.</span></span> <span data-ttu-id="d3f40-129">Чтобы отобразить наименования в алфавитном порядке, для столбца наименований используется испанская схема упорядочения.</span><span class="sxs-lookup"><span data-stu-id="d3f40-129">To display the titles in alphabetical order, you use a Spanish collating sequence for the title column.</span></span> <span data-ttu-id="d3f40-130">Конечный код SQL может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3f40-130">The resulting SQL might look like this:</span></span>  
  
    ```  
    SELECT title  
    FROM   
        authors   
        INNER JOIN   
            titleauthor   
            ON authors.au_id   
            =  titleauthor.au_id   
            INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
    WHERE   
         au_fname = 'Jaime' AND   
         au_lname = 'Pati??o'  
    ORDER BY   
         title COLLATE SQL_Spanish_Pref_CP1_CI_AS  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d3f40-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3f40-131">See Also</span></span>  
 <span data-ttu-id="d3f40-132">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d3f40-132">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d3f40-133">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d3f40-133">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
