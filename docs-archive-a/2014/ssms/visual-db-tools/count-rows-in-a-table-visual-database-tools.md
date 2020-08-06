---
title: Подсчет строк в таблице (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- totals [SQL Server], row counts
- row counts [SQL Server]
- column values [SQL Server]
- number of rows
- number of values
- counting rows
ms.assetid: dda4296a-1d16-4e77-8d6f-e295f6dd4e87
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6dca92fb955b776f56d9b51f28b1a486b89f18f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732217"
---
# <a name="count-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="e9bf0-102">подсчитать строки в таблице (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e9bf0-102">Count Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="e9bf0-103">Строки в таблице можно подсчитать, чтобы определить:</span><span class="sxs-lookup"><span data-stu-id="e9bf0-103">You can count rows in a table to determine:</span></span>  
  
-   <span data-ttu-id="e9bf0-104">общее число строк в таблице, например подсчет всех книг в таблице `titles` ;</span><span class="sxs-lookup"><span data-stu-id="e9bf0-104">The total number of rows in a table, for example, a count of all the books in a `titles` table.</span></span>  
  
-   <span data-ttu-id="e9bf0-105">количество строк в таблице, удовлетворяющих определенному условию (например количество книг одного издателя в таблице `titles` );</span><span class="sxs-lookup"><span data-stu-id="e9bf0-105">The number of rows in a table that meet a specific condition, for example, the number of books by one publisher in a `titles` table.</span></span>  
  
-   <span data-ttu-id="e9bf0-106">количество значений в определенном столбце.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-106">The number of values in a particular column.</span></span>  
  
 <span data-ttu-id="e9bf0-107">При подсчете значений в столбце значения NULL не учитываются.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-107">When you count values in a column, nulls are not included in the count.</span></span> <span data-ttu-id="e9bf0-108">Например можно подсчитать количество книг в таблице `titles` , имеющих значения в столбце `advance` .</span><span class="sxs-lookup"><span data-stu-id="e9bf0-108">For example, you might count the number of books in a `titles` table that have values in the `advance` column.</span></span> <span data-ttu-id="e9bf0-109">По умолчанию подсчет включает все значения, а не только уникальные.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-109">By default, the count includes all values, not just unique values.</span></span>  
  
 <span data-ttu-id="e9bf0-110">Процедуры выполнения для всех трех типов похожи.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-110">The procedures for all three types of counts are similar.</span></span>  
  
### <a name="to-count-all-the-rows-in-a-table"></a><span data-ttu-id="e9bf0-111">Подсчет всех строк в таблице</span><span class="sxs-lookup"><span data-stu-id="e9bf0-111">To count all the rows in a table</span></span>  
  
1.  <span data-ttu-id="e9bf0-112">Убедитесь, что таблица, по которой необходимо подвести итог, уже имеется на панели диаграмм.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-112">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="e9bf0-113">Щелкните правой кнопкой мыши фон панели диаграммы и выберите из контекстного меню пункт **Добавить Group By** .</span><span class="sxs-lookup"><span data-stu-id="e9bf0-113">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="e9bf0-114">[Конструктор запросов и представлений](visual-database-tools.md) добавляет столбец **Группировать** в сетку на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-114">The [Query and View Designer](visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="e9bf0-115">Выберите \*\* \* (все столбцы)\*\* в прямоугольнике, представляющем таблицу или возвращающий табличное значение объект.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-115">Select **\* (All Columns)** in the rectangle representing the table or table-valued object.</span></span>  
  
     <span data-ttu-id="e9bf0-116">Конструктор запросов и представлений автоматически заносит значение **Подсчет** в столбец **Group By** на панели критериев и присваивает столбцу, по которому подводится итог, псевдоним столбца.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-116">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="e9bf0-117">Псевдоним, созданный автоматически, можно заменить более содержательным псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-117">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="e9bf0-118">Дополнительные сведения см. в разделе [Создание псевдонимов столбцов (визуальные инструменты для баз данных)](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e9bf0-118">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="e9bf0-119">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-119">Run the query.</span></span>  
  
### <a name="to-count-all-the-rows-that-meet-a-condition"></a><span data-ttu-id="e9bf0-120">Подсчет всех строк, удовлетворяющих условию</span><span class="sxs-lookup"><span data-stu-id="e9bf0-120">To count all the rows that meet a condition</span></span>  
  
1.  <span data-ttu-id="e9bf0-121">Убедитесь, что таблица, по которой необходимо подвести итог, уже имеется на панели диаграмм.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-121">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="e9bf0-122">Щелкните правой кнопкой мыши фон панели диаграммы и выберите из контекстного меню пункт **Добавить Group By** .</span><span class="sxs-lookup"><span data-stu-id="e9bf0-122">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="e9bf0-123">Конструктор запросов и представлений добавляет столбец **Группировать** в сетку на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-123">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="e9bf0-124">Выберите \*\* \* (все столбцы)\*\* в прямоугольнике, представляющем таблицу или объект, структурированный табличным.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-124">Select **\*(All Columns)** in the rectangle representing the table or table-structured object.</span></span>  
  
     <span data-ttu-id="e9bf0-125">Конструктор запросов и представлений автоматически заносит значение **Подсчет** в столбец **Group By** на панели критериев и присваивает столбцу, по которому подводится итог, псевдоним столбца.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-125">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="e9bf0-126">О создании более содержательного заголовка столбца в выводе запроса см. в разделе [Создание псевдонимов столбцов (визуальные инструменты для баз данных)](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e9bf0-126">To create a more useful column heading in query output, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="e9bf0-127">Добавьте столбец данных, по которому необходимо произвести поиск, затем снимите флажок в столбце **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-127">Add the data column that you want to search, and then clear the check box in the **Output** column.</span></span>  
  
     <span data-ttu-id="e9bf0-128">Конструктор запросов и представлений автоматически заносит значение **Группировать** в столбец сетки **Group By** .</span><span class="sxs-lookup"><span data-stu-id="e9bf0-128">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
5.  <span data-ttu-id="e9bf0-129">Замените значение **Группировать** в столбце **Group By** на значение **Куда**.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-129">Change **Group By** in the **Group By** column to **Where**.</span></span>  
  
6.  <span data-ttu-id="e9bf0-130">В столбце **Фильтр** введите условие для выполнения поиска по столбцу данных.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-130">In the **Filter** column for the data column to search, enter the search condition.</span></span>  
  
7.  <span data-ttu-id="e9bf0-131">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-131">Run the query.</span></span>  
  
### <a name="to-count-the-values-in-a-column"></a><span data-ttu-id="e9bf0-132">Подсчет значений в столбце</span><span class="sxs-lookup"><span data-stu-id="e9bf0-132">To count the values in a column</span></span>  
  
1.  <span data-ttu-id="e9bf0-133">Убедитесь, что таблица, по которой необходимо подвести итог, уже имеется на панели диаграмм.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-133">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="e9bf0-134">Щелкните правой кнопкой мыши фон панели диаграммы и выберите из контекстного меню пункт **Добавить Group By** .</span><span class="sxs-lookup"><span data-stu-id="e9bf0-134">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="e9bf0-135">Конструктор запросов и представлений добавляет столбец **Группировать** в сетку на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-135">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="e9bf0-136">Добавьте столбец, по которому необходимо подвести итог, на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-136">Add the column that you want to count to the Criteria pane.</span></span>  
  
     <span data-ttu-id="e9bf0-137">Конструктор запросов и представлений автоматически заносит значение **Группировать** в столбец сетки **Group By** .</span><span class="sxs-lookup"><span data-stu-id="e9bf0-137">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
4.  <span data-ttu-id="e9bf0-138">Замените значение **Группировать** в столбце **Group By** на значение **Подсчет**.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-138">Change **Group By** in the **Group By** column to **Count**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e9bf0-139">Чтобы подсчитать только уникальные значения, выберите **Count Distinct**.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-139">To count only unique values, choose **Count Distinct**.</span></span>  
  
5.  <span data-ttu-id="e9bf0-140">Выполните запрос.</span><span class="sxs-lookup"><span data-stu-id="e9bf0-140">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9bf0-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9bf0-141">See Also</span></span>  
 <span data-ttu-id="e9bf0-142">[Сортировка и Группировка результатов запроса &#40;визуальных инструментов для баз данных&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e9bf0-142">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e9bf0-143">Резюмирование результатов запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e9bf0-143">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
