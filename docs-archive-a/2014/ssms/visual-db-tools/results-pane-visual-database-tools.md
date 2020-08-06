---
title: Панель результатов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- result sets [SQL Server], queries
- synchronization [SQL Server], query results with definition
- displaying query results in grid
- grid showing query results [SQL Server]
- showing query results in grid
- Query Designer [SQL Server], Results pane
- results [SQL Server], query
- viewing query results
- queries [SQL Server], results
- Results pane
ms.assetid: 6309a1bc-a628-4141-8bb5-b35924bd19f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: f0db32336931f74777be56befcde9501dc484b69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654706"
---
# <a name="results-pane-visual-database-tools"></a><span data-ttu-id="ef59a-102">Панель результатов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="ef59a-102">Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="ef59a-103">панель результатов отображает результаты самого последнего выполненного запроса SELECT</span><span class="sxs-lookup"><span data-stu-id="ef59a-103">The Results pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="ef59a-104">(результаты запросов других типов отображаются в окнах сообщений). Чтобы открыть панель результатов, откройте или создайте запрос или представление или получите данные таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef59a-104">(The results of other query types are displayed in message boxes.) To open the results pane, open or create a query or view or return a table's data.</span></span> <span data-ttu-id="ef59a-105">Если панель результатов не отображается по умолчанию, в меню **Конструктор запросов** выберите пункт **Панель**и щелкните **Результаты**.</span><span class="sxs-lookup"><span data-stu-id="ef59a-105">If the results pane doesn't show by default, from the **Query Designer** menu, point to **Pane**, and then click **Results**.</span></span>  
  
## <a name="what-you-can-do-in-the-results-pane"></a><span data-ttu-id="ef59a-106">Что можно делать на панели результатов:</span><span class="sxs-lookup"><span data-stu-id="ef59a-106">What You Can Do in the Results Pane</span></span>  
  
-   <span data-ttu-id="ef59a-107">Просматривать результирующие наборы самого последнего выполненного запроса SELECT в виде табличной сетки.</span><span class="sxs-lookup"><span data-stu-id="ef59a-107">View the result set for the most recently executed SELECT query in a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="ef59a-108">Для запросов или представлений, показывающих данные из отдельной таблицы или представления, можно редактировать значения отдельных столбцов результирующего набора, добавлять новые строки и удалять существующие.</span><span class="sxs-lookup"><span data-stu-id="ef59a-108">For queries or views that show data from a single table or view, you can edit the values in individual columns in the result set, add new rows, and delete existing rows.</span></span>  
  
## <a name="limitations-in-the-results-pane"></a><span data-ttu-id="ef59a-109">Ограничения, относящиеся к панели результатов</span><span class="sxs-lookup"><span data-stu-id="ef59a-109">Limitations in the Results Pane</span></span>  
  
-   <span data-ttu-id="ef59a-110">Результаты функций, возвращающих табличное значение, можно обновлять только в некоторых случаях.</span><span class="sxs-lookup"><span data-stu-id="ef59a-110">Results returned by table-valued functions can only be updated in some cases.</span></span>  
  
-   <span data-ttu-id="ef59a-111">Невозможно обновить запросы или представления, включающие столбцы из нескольких таблиц или представлений.</span><span class="sxs-lookup"><span data-stu-id="ef59a-111">Queries or views that include columns from more than one table or view cannot be updated.</span></span>  
  
-   <span data-ttu-id="ef59a-112">Нельзя обновлять результаты, возвращаемые хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="ef59a-112">Results returned by a stored procedure cannot be updated.</span></span>  
  
-   <span data-ttu-id="ef59a-113">Нельзя обновлять запросы или представления, содержащие предложения GROUP BY или DISTINCT</span><span class="sxs-lookup"><span data-stu-id="ef59a-113">Queries or views using the GROUP BY or DISTINCT clauses are not updatable.</span></span>  
  
## <a name="navigating-in-the-results-pane"></a><span data-ttu-id="ef59a-114">Перемещение по панели результатов</span><span class="sxs-lookup"><span data-stu-id="ef59a-114">Navigating in the Results Pane</span></span>  
 <span data-ttu-id="ef59a-115">Используя панель навигации в нижней части области результатов, можно быстро перемещаться по записям.</span><span class="sxs-lookup"><span data-stu-id="ef59a-115">You can quickly navigate through the records using the navigation bar at the bottom of the Results pane.</span></span>  
  
 <span data-ttu-id="ef59a-116">На панели имеются кнопки для перехода к первой и последней записи, к следующей и предыдущей записи, а также для перехода к конкретной записи.</span><span class="sxs-lookup"><span data-stu-id="ef59a-116">There are buttons for going to the first and last records, the next and previous records, and for going to a particular record.</span></span>  
  
 <span data-ttu-id="ef59a-117">Чтобы перейти к конкретной записи, наберите соответствующий номер строки в текстовом поле на панели навигации, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ef59a-117">To go to a particular record, type the number of the row in the text box in the navigation bar and then press ENTER.</span></span>  
  
 <span data-ttu-id="ef59a-118">Сведения об использовании сочетаний клавиш в конструкторе запросов и представлений см. в разделе [Навигация по конструктору запросов и представлений (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ef59a-118">For information about using keyboard shortcuts in the Query and View Designer see [Navigate in the Query and View Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="keeping-the-results-set-synchronized-with-the-query-definition"></a><span data-ttu-id="ef59a-119">Синхронизация наборов результатов с определением запроса</span><span class="sxs-lookup"><span data-stu-id="ef59a-119">Keeping the Results Set Synchronized with the Query Definition</span></span>  
 <span data-ttu-id="ef59a-120">Во время работы с результатами запроса или представления существует вероятность, что записи на панели результатов окажутся не синхронизированы с определением запроса.</span><span class="sxs-lookup"><span data-stu-id="ef59a-120">While you are working on the results of a query or view it is possible for the records in the results pane to get out of synchronization with the query's definition.</span></span> <span data-ttu-id="ef59a-121">Например, при выполнении запроса для четырех из пяти столбцов таблицы и последующего добавления пятого столбца к определению запроса на панели диаграмм, данные этого пятого столбца не будут автоматически добавлены на панель результатов.</span><span class="sxs-lookup"><span data-stu-id="ef59a-121">For example, if you run a query for four out of five columns in a table, and then use the Diagram pane to add the fifth column to the definition of the query, that fifth column's data will not automatically be added to the Results pane.</span></span> <span data-ttu-id="ef59a-122">Чтобы на панели результатов отображалось новое определение запроса, необходимо запустить запрос снова.</span><span class="sxs-lookup"><span data-stu-id="ef59a-122">To make the results pane reflect the new query definition, run the query again.</span></span>  
  
 <span data-ttu-id="ef59a-123">Если запрос изменился, в правом нижнем углу панели результатов появляется значок предупреждения и текст «Запрос изменен».</span><span class="sxs-lookup"><span data-stu-id="ef59a-123">If a query changes, an alert icon and the text "Query Changed" appears in the lower-right corner of the results pane.</span></span> <span data-ttu-id="ef59a-124">Изображение значка появляется также в левом верхнем углу панели.</span><span class="sxs-lookup"><span data-stu-id="ef59a-124">The icon is repeated in the upper-left corner of the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef59a-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="ef59a-125">See Also</span></span>  
 <span data-ttu-id="ef59a-126">[Создание запросов &#40;визуальных инструментов для баз данных&#41;](create-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ef59a-126">[Create Queries &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="ef59a-127">[Выполнение запросов &#40;визуальных инструментов для баз данных&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ef59a-127">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="ef59a-128">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ef59a-128">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="ef59a-129">[Панель диаграмм &#40;визуальные инструменты для баз данных&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ef59a-129">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="ef59a-130">[Панель критериев &#40;визуальных инструментов для баз данных&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ef59a-130">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ef59a-131">Работа с данными на панели результатов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="ef59a-131">Work with Data in the Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
