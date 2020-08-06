---
title: Инструменты конструктора запросов и представлений (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.querydesigner
- vdt.pane.diagram
- vdt.pane.grid
- vdt.dlgbox.querybuilder
- vdt.pane.sql
- vdt.pane.results
helpviewer_keywords:
- Query Designer [SQL Server], panes
- View Designer, panes
- Query Designer [SQL Server], components
- View Designer, components
ms.assetid: 12e4b5a5-b793-4b6c-a0e5-c450c49bf26f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 29bd3fa9e171551197927aae0d1bc00446df6e7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735830"
---
# <a name="query-and-view-designer-tools-visual-database-tools"></a><span data-ttu-id="f37d4-102">Инструменты конструктора запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="f37d4-102">Query and View Designer Tools (Visual Database Tools)</span></span>
  <span data-ttu-id="f37d4-103">При конструировании запроса, представления, встроенной функции или хранимой процедуры, состоящей из одной инструкции, окно конструктора состоит из четырех панелей: панель диаграмм, область критериев, панель «SQL» и панель результатов.</span><span class="sxs-lookup"><span data-stu-id="f37d4-103">When you design a query, view, in-line function, or single-statement stored procedure, the designer you use consists of four panes: the Diagram pane, the Criteria pane, the SQL pane, and the Results pane.</span></span>  
  
 <span data-ttu-id="f37d4-104">![Конструктор запросов](../../database-engine/media//vs-queryviewdsgpanes.gif "Конструктор запросов")</span><span class="sxs-lookup"><span data-stu-id="f37d4-104">![Query Designer](../../database-engine/media//vs-queryviewdsgpanes.gif "Query Designer")</span></span>  
  
-   <span data-ttu-id="f37d4-105">Панель диаграмм отображает запрашиваемые таблицы и другие возвращающие табличное значение объекты.</span><span class="sxs-lookup"><span data-stu-id="f37d4-105">The Diagram pane displays the tables and other table-valued objects that you are querying.</span></span> <span data-ttu-id="f37d4-106">Каждый прямоугольник представляет таблицу или возвращающий табличное значение объект и показывает доступные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="f37d4-106">Each rectangle represents a table or table-valued object and shows the available data columns.</span></span> <span data-ttu-id="f37d4-107">Соединения обозначены линиями между прямоугольниками.</span><span class="sxs-lookup"><span data-stu-id="f37d4-107">Joins are indicated by lines between the rectangles.</span></span> <span data-ttu-id="f37d4-108">Дополнительные сведения см. в разделе [Панель диаграммы (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f37d4-108">For more information, see [Diagram Pane &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="f37d4-109">Панель «Критерии» содержит сетку, подобную электронной таблице, в которой указываются параметры, например какие столбцы данных нужно отображать, какие строки выбирать, как группировать строки и так далее.</span><span class="sxs-lookup"><span data-stu-id="f37d4-109">The Criteria pane contains a spreadsheet-like grid in which you specify options, such as which data columns to display, what rows to select, how to group rows, and so on.</span></span> <span data-ttu-id="f37d4-110">Дополнительные сведения см. в разделе [Панель критериев (визуальные инструменты для баз данных)](criteria-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f37d4-110">For more information, see [Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="f37d4-111">Панель «SQL» отображает инструкции SQL для запроса или представления.</span><span class="sxs-lookup"><span data-stu-id="f37d4-111">The SQL pane displays the SQL statement for the query or view.</span></span> <span data-ttu-id="f37d4-112">Можно редактировать инструкцию SQL, созданную конструктором, или можно ввести собственную инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="f37d4-112">You can edit the SQL statement created by the Designer or you can enter your own SQL statement.</span></span> <span data-ttu-id="f37d4-113">Это особенно полезно для ввода инструкций SQL, которые не могут быть созданы с помощью панелей диаграмм и критериев, например запросы объединения.</span><span class="sxs-lookup"><span data-stu-id="f37d4-113">It is particularly useful for entering SQL statements that cannot be created using the Diagram and Criteria panes, such as union queries.</span></span> <span data-ttu-id="f37d4-114">Дополнительные сведения см. в разделе [Панель SQL (визуальные инструменты для баз данных)](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f37d4-114">For more information, see [SQL Pane &#40;Visual Database Tools&#41;](sql-pane-visual-database-tools.md).</span></span>  
  
-   <span data-ttu-id="f37d4-115">Панель «Результаты» показывает сетку с данными, полученными запросом или представлением.</span><span class="sxs-lookup"><span data-stu-id="f37d4-115">The Results pane shows a grid with data retrieved by the query or view.</span></span> <span data-ttu-id="f37d4-116">В конструкторе запросов и представлений панель показывает результаты последнего выполненного запроса SELECT.</span><span class="sxs-lookup"><span data-stu-id="f37d4-116">In the Query and View Designer, the pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="f37d4-117">Можно изменить базу данных, изменяя значения в ячейках сетки, а также добавлять или удалять строки.</span><span class="sxs-lookup"><span data-stu-id="f37d4-117">You can modify the database by editing values in the cells of the grid, and you can add or delete rows.</span></span> <span data-ttu-id="f37d4-118">Дополнительные сведения см. в разделе [Панель результатов (визуальные инструменты для баз данных)](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f37d4-118">For more information, see [Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="f37d4-119">Можно создать запрос или представление, работая на любой из панелей: можно указать столбец для отображения, выбрав его на панели диаграмм, введя его в области критериев или сделав его частью инструкции SQL на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="f37d4-119">You can create a query or view by working in any of the panes: you can specify a column to display by choosing it in the Diagram pane, entering it into the Criteria pane, or making it part of the SQL statement in the SQL pane.</span></span>  
  
## <a name="displaying-and-hiding-panes"></a><span data-ttu-id="f37d4-120">Отображение и скрытие панелей</span><span class="sxs-lookup"><span data-stu-id="f37d4-120">Displaying and Hiding Panes</span></span>  
 <span data-ttu-id="f37d4-121">Для скрытия или отображения невидимой панели щелкните правой кнопкой мыши панель конструктора, выберите пункт **Панель**, затем щелкните имя панели.</span><span class="sxs-lookup"><span data-stu-id="f37d4-121">To hide a pane or display a pane that is not visible, right-click the design surface, point to **Pane**, and then click the name of the pane.</span></span> <span data-ttu-id="f37d4-122">Если конструктор запросов и представлений открыт в режиме конструктора запросов, панель **Результаты** недоступна.</span><span class="sxs-lookup"><span data-stu-id="f37d4-122">If the Query and View Designer is opened in Query Designer mode, the **Results** pane is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f37d4-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f37d4-123">See Also</span></span>  
 <span data-ttu-id="f37d4-124">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f37d4-124">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="f37d4-125">[Откройте конструктор запросов и представлений &#40;визуальные инструменты для баз данных&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f37d4-125">[Open the Query and View Designer &#40;Visual Database Tools&#41;](open-the-query-and-view-designer-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="f37d4-126">Редактор SQL (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="f37d4-126">SQL Editor &#40;Visual Database Tools&#41;</span></span>](sql-editor-visual-database-tools.md)  
  
  
