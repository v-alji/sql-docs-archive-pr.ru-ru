---
title: Добавление столбцов в запросы (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- queries [SQL Server], columns
- adding columns
ms.assetid: 82f3ba72-3d72-4fb1-8179-2a953a782787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 49c6e575eea2d4437be1f16b400ca22120471fcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657480"
---
# <a name="add-columns-to-queries-visual-database-tools"></a><span data-ttu-id="4e0b7-102">Добавление столбцов в запросы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="4e0b7-102">Add Columns to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="4e0b7-103">Для использования столбца в запросе его необходимо туда добавить.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-103">To use a column in a query, you must add it to the query.</span></span> <span data-ttu-id="4e0b7-104">Можно добавлять столбцы для отображения в результатах выполнения запроса, для использования при сортировке, поиска или обобщения их содержимого.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-104">You might add a column to display it in query output, to use it for sorting, to search the contents of the column, or to summarize its contents.</span></span> <span data-ttu-id="4e0b7-105">Выбрать, какие используемые в запросе столбцы необходимо включить на панель результатов, можно при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-105">You can decide which of the columns you use in the query are included in the results pane when the query is run.</span></span> <span data-ttu-id="4e0b7-106">Дополнительные сведения см. в разделе [Удаление столбцов из результатов запроса (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4e0b7-106">For more information see [Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e0b7-107">Для просмотра типа данных столбца в конструкторе запросов и представлений выберите таблицу или возвращающий табличное значение объект на **панели диаграммы** , а затем щелкните "Список столбцов" в окне свойств.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-107">To view the data type of a column in Query and View Designer; select the table or table-valued object in the **Diagram Pane** and in the properties window click Column List.</span></span> <span data-ttu-id="4e0b7-108">После этого нажмите кнопку с многоточием **(...)** , чтобы открыть диалоговое окно **Список столбцов**.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-108">Then click the **ellipses (...)** to open the **Column List** dialog box.</span></span>  
  
 <span data-ttu-id="4e0b7-109">При работе со столбцами в запросе можно также применять выражение, состоящее из любого сочетания столбцов, литералов, операторов и функций.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-109">Wherever you use a column in a query, you can also use an expression that can consist of any combination of columns, literals, operators, and functions.</span></span>  
  
### <a name="to-add-an-individual-column"></a><span data-ttu-id="4e0b7-110">Добавление отдельного столбца</span><span class="sxs-lookup"><span data-stu-id="4e0b7-110">To add an individual column</span></span>  
  
-   <span data-ttu-id="4e0b7-111">На **панели диаграммы**установите флажок рядом со столбцом, который требуется включить.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-111">In the **Diagram Pane**, select the check box next to the column that you want to include.</span></span>  
  
     <span data-ttu-id="4e0b7-112">-или-</span><span class="sxs-lookup"><span data-stu-id="4e0b7-112">-or-</span></span>  
  
-   <span data-ttu-id="4e0b7-113">На **панели критериев**перейдите на первую пустую строку сетки, щелкните поле в столбце **Столбец** и выберите имя столбца из раскрывающего списка.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-113">In the **Criteria Pane**, move to the first blank grid row, click the field in the **Column** column, and select a column name from the drop-down list.</span></span>  
  
### <a name="to-add-all-columns-for-one-table-or-table-valued-object"></a><span data-ttu-id="4e0b7-114">Добавление всех столбцов одной таблицы или возвращающего табличное значение объекта</span><span class="sxs-lookup"><span data-stu-id="4e0b7-114">To add all columns for one table or table-valued object</span></span>  
  
-   <span data-ttu-id="4e0b7-115">На **панели диаграмм**установите флажок рядом с полем \*\* \* (все столбцы)\*\*.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-115">In the **Diagram Pane**, select the check box next to **\*(All Columns)**.</span></span>  
  
### <a name="to-add-all-columns-for-all-tables-and-table-structured-objects"></a><span data-ttu-id="4e0b7-116">Добавление всех столбцов всех таблиц и табличных объектов</span><span class="sxs-lookup"><span data-stu-id="4e0b7-116">To add all columns for all tables and table-structured objects</span></span>  
  
1.  <span data-ttu-id="4e0b7-117">Убедитесь, что строки соединения не выбраны на **панели операций с таблицей** .</span><span class="sxs-lookup"><span data-stu-id="4e0b7-117">Make sure no join lines in the **Table Operations Pane** are selected.</span></span>  
  
2.  <span data-ttu-id="4e0b7-118">Щелкните правой кнопкой мыши пустую область окна проектирования и выберите пункт **Свойства** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-118">Right-click in the empty space of the Design window and choose **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="4e0b7-119">В окне "Свойства" щелкните **Выводить все столбцы** и выберите **Да** или **Нет** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="4e0b7-119">In the Properties window click **Output all columns** and choose **Yes** or **No** from the dropdown list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0b7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e0b7-120">See Also</span></span>  
 <span data-ttu-id="4e0b7-121">[Удаление столбцов из результатов запроса &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4e0b7-121">[Remove Columns from Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="4e0b7-122">[Удаление столбцов из запросов &#40;визуальных инструментов для баз данных&#41;](remove-columns-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4e0b7-122">[Remove Columns from Queries &#40;Visual Database Tools&#41;](remove-columns-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4e0b7-123">[Укажите условия поиска &#40;визуальные инструменты для баз данных&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4e0b7-123">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4e0b7-124">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4e0b7-124">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4e0b7-125">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="4e0b7-125">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
