---
title: Создание запроса на создание таблицы (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- table creation [SQL Server], Make Table query
- inserting tables
- Make Table query
- adding tables
ms.assetid: 4493cffa-7b2d-4c24-8ef0-d49329198972
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91c4a3bf45935053789d6e884b1af5b338b4c7c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731285"
---
# <a name="create-make-table-queries-visual-database-tools"></a><span data-ttu-id="9b2e3-102">Создание запроса на создание таблицы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9b2e3-102">Create Make Table Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="9b2e3-103">При помощи запросов на создание таблицы в новую таблицу можно копировать строки, что может оказаться полезным для создания подмножества данных и копирования содержимого таблиц из одной базы данных в другую.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-103">You can copy rows into a new table using a Make Table query, which is useful for creating subsets of data to work with or copying the contents of a table from one database to another.</span></span> <span data-ttu-id="9b2e3-104">Запрос на создание таблицы похож на запрос на вставку результатов, но создает новую таблицу, в которую затем копируются строки.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-104">A Make Table query is similar to an Insert Results query but creates a new table to copy rows into.</span></span>  
  
 <span data-ttu-id="9b2e3-105">При создании запроса на создание таблицы указывают:</span><span class="sxs-lookup"><span data-stu-id="9b2e3-105">When you create a Make Table query, you specify:</span></span>  
  
-   <span data-ttu-id="9b2e3-106">Имя новой таблицы базы данных (целевой таблицы).</span><span class="sxs-lookup"><span data-stu-id="9b2e3-106">The name of the new database table (the destination table).</span></span>  
  
-   <span data-ttu-id="9b2e3-107">Таблицу или таблицы, из которых копируются строки (исходную таблицу).</span><span class="sxs-lookup"><span data-stu-id="9b2e3-107">The table or tables to copy rows from (the source table).</span></span> <span data-ttu-id="9b2e3-108">Можно копировать данные из одной таблицы или из соединенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-108">You can copy from a single table or from joined tables.</span></span>  
  
-   <span data-ttu-id="9b2e3-109">Столбцы в исходной таблице, содержимое которых нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-109">The columns in the source table whose contents you want to copy.</span></span>  
  
-   <span data-ttu-id="9b2e3-110">Порядок сортировки, когда нужно скопировать строки в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-110">Sort order, if you want to copy the rows in a particular order.</span></span>  
  
-   <span data-ttu-id="9b2e3-111">Условия поиска для выборки строк, которые нужно скопировать.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-111">Search conditions to define the rows you want to copy.</span></span>  
  
-   <span data-ttu-id="9b2e3-112">Параметры группировки для случаев, когда нужно скопировать только сводные данные.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-112">Group By options, if you want to copy only summary information.</span></span>  
  
 <span data-ttu-id="9b2e3-113">Например следующий запрос создает новую таблицу с именем `uk`_`customers` и копирует в нее данные из таблицы `customers` :</span><span class="sxs-lookup"><span data-stu-id="9b2e3-113">For example, the following query creates a new table called `uk`_`customers` and copies information from the `customers` table to it:</span></span>  
  
```  
SELECT *   
INTO uk_customers  
FROM customers  
WHERE country = 'UK'  
```  
  
 <span data-ttu-id="9b2e3-114">Для успешного выполнения запроса на создание таблицы:</span><span class="sxs-lookup"><span data-stu-id="9b2e3-114">In order to use a Make Table query successfully:</span></span>  
  
-   <span data-ttu-id="9b2e3-115">база данных должна поддерживать синтаксис SELECT...INTO;</span><span class="sxs-lookup"><span data-stu-id="9b2e3-115">Your database must support the SELECT...INTO syntax.</span></span>  
  
-   <span data-ttu-id="9b2e3-116">необходимо разрешение на создание таблицы в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-116">You must have permission to create a table in the target database.</span></span>  
  
### <a name="to-create-a-make-table-query"></a><span data-ttu-id="9b2e3-117">Создание запроса на создание таблицы</span><span class="sxs-lookup"><span data-stu-id="9b2e3-117">To create a Make Table query</span></span>  
  
1.  <span data-ttu-id="9b2e3-118">Добавьте на панели «Диаграмма» исходную таблицу или таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-118">Add the source table or tables to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="9b2e3-119">В меню **Конструктор запросов** наведите указатель на пункт **Тип изменения**, а затем выберите пункт **Создать таблицу**.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-119">From the **Query Designer** menu, point to **Change Type**, and then click **Make Table**.</span></span>  
  
3.  <span data-ttu-id="9b2e3-120">В диалоговом окне **Создать таблицу** введите имя целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-120">In the **Make Table** dialog box, type the name of the destination table.</span></span> <span data-ttu-id="9b2e3-121">Конструктор запросов и представлений не проверяет, есть ли уже такое имя и имеется ли разрешение на создание таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-121">The Query and View Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
     <span data-ttu-id="9b2e3-122">Чтобы создать целевую таблицу в другой базе данных, укажите полное имя целевой таблицы, состоящее из имени целевой базы данных, имени владельца (если требуется) и имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-122">To create a destination table in another database, specify a fully qualified table name including the name of the target database, the owner (if required), and the name of the table.</span></span>  
  
4.  <span data-ttu-id="9b2e3-123">Укажите столбцы, из которых будут копироваться данные, добавив их к запросу.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-123">Specify the columns to copy by adding them to the query.</span></span> <span data-ttu-id="9b2e3-124">Дополнительные сведения см. в разделе [Добавление столбцов в запросы (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9b2e3-124">For details, see [Add Columns to Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span> <span data-ttu-id="9b2e3-125">Копируются только те столбцы, которые добавлены в запрос.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-125">Columns will be copied only if you add them to the query.</span></span> <span data-ttu-id="9b2e3-126">Чтобы скопировать целые строки, выберите \*\* \* (все столбцы)\*\*.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-126">To copy entire rows, choose **\* (All Columns)**.</span></span>  
  
     <span data-ttu-id="9b2e3-127">Конструктор запросов и представлений добавляет выбранные столбцы к столбцу **Столбец** панели критериев.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-127">The Query and View Designer adds the columns you choose to the **Column** column of the Criteria pane.</span></span>  
  
5.  <span data-ttu-id="9b2e3-128">Чтобы скопировать строки в определенном порядке, укажите порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-128">If you want to copy rows in a particular order, specify a sort order.</span></span> <span data-ttu-id="9b2e3-129">Дополнительные сведения см. в разделе **Сортировка и группирование результатов запроса**.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-129">For details, see **Sorting and Grouping Query Results**.</span></span>  
  
6.  <span data-ttu-id="9b2e3-130">Укажите, какие строки необходимо копировать, введя условия поиска.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-130">Specify the rows to copy by entering search conditions.</span></span> <span data-ttu-id="9b2e3-131">Дополнительные сведения см. в разделе [Определение критериев поиска (визуальные инструменты для баз данных)](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9b2e3-131">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="9b2e3-132">Если условия поиска не заданы, в целевую таблицу будут скопированы все строки исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-132">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b2e3-133">При добавления столбца для поиска на панели критериев конструктор запросов и представлений также включит его в список столбцов, подлежащих копированию.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-133">When you add a column to search to the Criteria pane, the Query and View Designer also adds it to the list of columns to copy.</span></span> <span data-ttu-id="9b2e3-134">Если столбец необходим для поиска, но копировать его не нужно, снимите флажок рядом с именем этого столбца в прямоугольнике, представляющем таблицу или объект со структурой таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-134">If you want to use a column for searching but not copy it, clear the check box next to the column name in the rectangle representing the table or table-structured object.</span></span>  
  
7.  <span data-ttu-id="9b2e3-135">Чтобы скопировать сводные данные, укажите параметры Group By.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-135">If you want to copy summary information, specify Group By options.</span></span> <span data-ttu-id="9b2e3-136">Дополнительные сведения см. в разделе [Резюмирование результатов запросов (визуальные инструменты для баз данных)](summarize-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9b2e3-136">For details, see [Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="9b2e3-137">При выполнении запроса на создание таблицы в [панели результатов](results-pane-visual-database-tools.md)не выводятся никакие результаты.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-137">When you execute a Make Table query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="9b2e3-138">Вместо этого появляется сообщение о количестве скопированных строк.</span><span class="sxs-lookup"><span data-stu-id="9b2e3-138">Instead, a message appears indicating how many rows were copied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2e3-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b2e3-139">See Also</span></span>  
 <span data-ttu-id="9b2e3-140">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9b2e3-140">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9b2e3-141">Типы запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9b2e3-141">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
