---
title: Работа со столбцами в агрегатных запросах (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query summary results
- GROUP BY clause, query summary results
- aggregate queries [SQL Server]
- WHERE clause, query summary results
ms.assetid: 1b82681f-3d4f-4b9a-bb1d-2060e44f2577
author: stevestein
ms.author: sstein
ms.openlocfilehash: 880f7529cebd7f51951e62952e3b5f13190f99b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727714"
---
# <a name="work-with-columns-in-aggregate-queries-visual-database-tools"></a><span data-ttu-id="49f9f-102">Работа со столбцами в агрегатных запросах (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="49f9f-102">Work with Columns in Aggregate Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="49f9f-103">[Конструктор запросов и представлений](visual-database-tools.md) делает некоторые предположения для создания правильного статистического запроса.</span><span class="sxs-lookup"><span data-stu-id="49f9f-103">When you create aggregate queries the [Query and View Designer](visual-database-tools.md) makes certain assumptions so that it can construct a valid query.</span></span> <span data-ttu-id="49f9f-104">Например, если при создании статистического запроса помечается столбец данных для вывода, конструктор запросов и представлений автоматически включает этот столбец в предложение GROUP BY, чтобы в итоговых результатах случайно не было отображено содержимое отдельной строки.</span><span class="sxs-lookup"><span data-stu-id="49f9f-104">For example, if you are creating an aggregate query and mark a data column for output, the Query and View Designer automatically makes the column part of the GROUP BY clause so that you do not inadvertently attempt to display the contents of an individual row in a summary.</span></span>  
  
## <a name="using-group-by"></a><span data-ttu-id="49f9f-105">Параметр «Группировать по»</span><span class="sxs-lookup"><span data-stu-id="49f9f-105">Using Group By</span></span>  
 <span data-ttu-id="49f9f-106">Конструктор запросов и представлений использует следующие правила для работы со столбцами:</span><span class="sxs-lookup"><span data-stu-id="49f9f-106">The Query and View Designer uses the following guidelines for working with columns:</span></span>  
  
-   <span data-ttu-id="49f9f-107">При выборе параметра «Группировать по» или добавлении агрегатной функции в запрос все столбцы, помеченные для вывода или используемые для сортировки, автоматически добавляются в предложение GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="49f9f-107">When you choose the Group By option or add an aggregate function to a query, all columns marked for output or used for sorting are automatically added to the GROUP BY clause.</span></span> <span data-ttu-id="49f9f-108">Столбцы не добавляются автоматически в предложение GROUP BY, если они уже являются частью агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="49f9f-108">Columns are not automatically added to the GROUP BY clause if they are already part of an aggregate function.</span></span>  
  
     <span data-ttu-id="49f9f-109">Если нужно, чтобы определенный столбец не входил в предложение GROUP BY, необходимо вручную изменить его, выбрав другой параметр в столбце «Группировать по» на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="49f9f-109">If you do not want a particular column to be part of the GROUP BY clause, you must manually change it by selecting a different option in the Group By column of the Criteria pane.</span></span> <span data-ttu-id="49f9f-110">Однако конструктор запросов и представлений не будет препятствовать выбору параметра, который приведет к невозможности выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="49f9f-110">However, the Query and View Designer will not prevent you from choosing an option that can result in a query that will not run.</span></span>  
  
-   <span data-ttu-id="49f9f-111">Если выходной столбец добавлен в агрегатную функцию вручную на панели критериев или SQL, конструктор запросов и представлений не удалит автоматически другие выходные столбцы из запроса.</span><span class="sxs-lookup"><span data-stu-id="49f9f-111">If you manually add a query output column to an aggregate function in either the Criteria or SQL pane, the Query and View Designer does not automatically remove other output columns from the query.</span></span> <span data-ttu-id="49f9f-112">Поэтому нужно удалить оставшиеся столбцы из вывода запроса или включить их в предложение GROUP BY либо в агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="49f9f-112">Therefore, you must remove the remaining columns from the query output or make them part of the GROUP BY clause or of an aggregate function.</span></span>  
  
 <span data-ttu-id="49f9f-113">При вводе условия поиска в столбец «Фильтр» на панели критериев конструктор запросов и представлений следует таким правилам:</span><span class="sxs-lookup"><span data-stu-id="49f9f-113">When you enter a search condition into the Filter column of the Criteria pane, the Query and View Designer follows these rules:</span></span>  
  
-   <span data-ttu-id="49f9f-114">Если столбец **Группировать** сетки не отображен (так как статистический запрос еще не указан), условие поиска помещается в предложение WHERE.</span><span class="sxs-lookup"><span data-stu-id="49f9f-114">If the **Group By** column of the grid is not displayed (because you have not yet specified an aggregate query), the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="49f9f-115">Если статистический запрос уже задан и выбран параметр **Где** столбца **Группировать** , условие поиска помещается в предложение WHERE.</span><span class="sxs-lookup"><span data-stu-id="49f9f-115">If you are already in an aggregate query and have selected the option **Where** in the **Group By** column, the search condition is placed into the WHERE clause.</span></span>  
  
-   <span data-ttu-id="49f9f-116">Если столбец **Группировать** содержит любые значения, отличные от **Где**, условие поиска помещается в предложение HAVING.</span><span class="sxs-lookup"><span data-stu-id="49f9f-116">If the **Group By** column contains any value other than **Where**, the search condition is placed in the HAVING clause.</span></span>  
  
## <a name="using-the-having-and-where-clauses"></a><span data-ttu-id="49f9f-117">Использование предложений HAVING и WHERE</span><span class="sxs-lookup"><span data-stu-id="49f9f-117">Using the HAVING and WHERE Clauses</span></span>  
 <span data-ttu-id="49f9f-118">Следующие принципы описывают, как можно использовать столбцы в условиях поиска статистического запроса.</span><span class="sxs-lookup"><span data-stu-id="49f9f-118">The following principles describe how you can reference columns in an aggregate query in search conditions.</span></span> <span data-ttu-id="49f9f-119">Обычно можно использовать столбец в условии поиска для фильтрации строк, по которым должны быть подведены итоги (предложение WHERE), или чтобы определить, какие сгруппированные результаты появятся в конечном выводе (предложение HAVING).</span><span class="sxs-lookup"><span data-stu-id="49f9f-119">In general, you can use a column in a search condition to filter the rows that should be summarized (a WHERE clause) or to determine which grouped results appear in the final output (a HAVING clause).</span></span>  
  
-   <span data-ttu-id="49f9f-120">Отдельные столбцы данных могут появляться как в предложениях WHERE, так и в предложениях HAVING в зависимости от того, как они используются в других частях запроса.</span><span class="sxs-lookup"><span data-stu-id="49f9f-120">Individual data columns can appear in either the WHERE or HAVING clause, depending on how they are used elsewhere in the query.</span></span>  
  
-   <span data-ttu-id="49f9f-121">Предложения WHERE используются для выбора поднабора строк для подведения итогов или группировки и, следовательно, применяются перед любой группировкой.</span><span class="sxs-lookup"><span data-stu-id="49f9f-121">WHERE clauses are used to select a subset of rows for summarizing and grouping and are thus applied before any grouping is done.</span></span> <span data-ttu-id="49f9f-122">Поэтому можно использовать столбец данных в предложении WHERE, даже если он не указан в предложении GROUP BY или не содержится в агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="49f9f-122">Therefore, you can use a data column in a WHERE clause even if it is not part of the GROUP BY clause or contained in an aggregate function.</span></span> <span data-ttu-id="49f9f-123">Например, следующая инструкция выбирает все наименования, стоимость которых больше чем 10,00 $ и вычисляет среднюю цену:</span><span class="sxs-lookup"><span data-stu-id="49f9f-123">For example, the following statement selects all titles that cost more than $10.00 and averages the price:</span></span>  
  
    ```  
    SELECT AVG(price)  
    FROM titles  
    WHERE price > 10  
    ```  
  
-   <span data-ttu-id="49f9f-124">Если создается условие поиска со столбцом, используемым также в предложении GROUP BY или в агрегатной функции, это условие может быть указано в предложении WHERE или HAVING. Предложение выбирает пользователь, когда создает условие.</span><span class="sxs-lookup"><span data-stu-id="49f9f-124">If you create a search condition that involves a column also used in a GROUP BY clause or aggregate function, the search condition can appear as either a WHERE clause or a HAVING clause - you can decide which when you create the condition.</span></span> <span data-ttu-id="49f9f-125">Например, следующая инструкция создает среднюю цену для наименований для каждого издателя и потом отображает среднее по издателям, у которых средняя цена больше чем 10,00 $:</span><span class="sxs-lookup"><span data-stu-id="49f9f-125">For example, the following statement creates an average price for the titles for each publisher, then displays the average for the publishers in which the average price is greater than $10.00:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
    ```  
  
-   <span data-ttu-id="49f9f-126">Если в условии поиска используется агрегатная функция, это условие затрагивает сводку и поэтому должно быть указано в предложении HAVING.</span><span class="sxs-lookup"><span data-stu-id="49f9f-126">If you use an aggregate function in a search condition, the condition involves a summary and must therefore be part of the HAVING clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f9f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="49f9f-127">See Also</span></span>  
 <span data-ttu-id="49f9f-128">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="49f9f-128">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="49f9f-129">Результаты запросов сортировки и группирования (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="49f9f-129">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
