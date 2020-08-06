---
title: Добавление таблиц в запросы (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
- queries [SQL Server], tables
ms.assetid: 6551aa7e-31a1-4636-852a-819bc53d658b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 572002bc913cc9916a75ce2b16c12064452d250f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664652"
---
# <a name="add-tables-to-queries-visual-database-tools"></a><span data-ttu-id="e4e01-102">Добавление таблиц в запросы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e4e01-102">Add Tables to Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="e4e01-103">При создании запроса извлекаются данные из таблицы или других объектов, структурированных подобно таблицам, таких как представления и некоторые пользовательские функции.</span><span class="sxs-lookup"><span data-stu-id="e4e01-103">When you create a query, you are retrieving data from a table or other objects structured like tables - views and certain user-defined functions.</span></span> <span data-ttu-id="e4e01-104">Чтобы любые из этих объектов можно было использовать в запросе, их следует добавить на **панель диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="e4e01-104">To work with any of these objects in your query, you add them to the **Diagram Pane**.</span></span>  
  
### <a name="to-add-a-table-or-table-valued-object-to-a-query"></a><span data-ttu-id="e4e01-105">Добавление таблицы или возвращающего табличное значение объекта в запрос</span><span class="sxs-lookup"><span data-stu-id="e4e01-105">To add a table or table-valued object to a query</span></span>  
  
1.  <span data-ttu-id="e4e01-106">Щелкните правой кнопкой мыши **панель диаграммы** конструктора запросов и представлений и выберите в контекстом меню пункт **Добавить таблицу** .</span><span class="sxs-lookup"><span data-stu-id="e4e01-106">In the **Diagram pane** of the Query and View Designer, right-click the background and choose **Add Table** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="e4e01-107">В диалоговом окне **Добавление таблицы** выберите вкладку, соответствующую типу объекта, который нужно добавить в запрос.</span><span class="sxs-lookup"><span data-stu-id="e4e01-107">In the **Add Table** dialog box, select the tab for the type of object you want to add to the query.</span></span>  
  
3.  <span data-ttu-id="e4e01-108">В списке элементов дважды щелкните каждый элемент, который нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="e4e01-108">In the list of items, double-click each item you want to add.</span></span>  
  
4.  <span data-ttu-id="e4e01-109">Завершив добавление элементов, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e4e01-109">When you finish adding items, click **Close**.</span></span>  
  
     <span data-ttu-id="e4e01-110">После этого конструктор запросов и представлений обновит соответствующим образом **панель диаграммы**, **панель критериев**и **панель SQL** .</span><span class="sxs-lookup"><span data-stu-id="e4e01-110">The Query and View Designer updates the **Diagram Pane**, **Criteria Pane**, and **SQL Pane** accordingly.</span></span>  
  
 <span data-ttu-id="e4e01-111">Таблицы и представления автоматически добавляются в запрос при ссылке на них в инструкции, вводимой на панели SQL</span><span class="sxs-lookup"><span data-stu-id="e4e01-111">Tables and views are automatically added to the query when you reference them in the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="e4e01-112">Конструктор запросов и представлений не отображает столбцы таблицы или табличного объекта, если недостаточно прав для этого или если поставщик не может возвратить информацию о них.</span><span class="sxs-lookup"><span data-stu-id="e4e01-112">The Query and View Designer will not display data columns for a table or table-structured object if you do not have sufficient access rights to it or if the provider cannot return information about it.</span></span> <span data-ttu-id="e4e01-113">В таких случаях для таблицы или возвращающего табличное значение объекта отображаются только заголовок окна и флажок \* (Все столбцы).</span><span class="sxs-lookup"><span data-stu-id="e4e01-113">In such cases, only a title bar and the \* (All Columns) check box are displayed for the table or table-valued object.</span></span>  
  
### <a name="to-add-an-existing-query-to-a-new-query"></a><span data-ttu-id="e4e01-114">Добавление существующего запроса в новый запрос</span><span class="sxs-lookup"><span data-stu-id="e4e01-114">To add an existing query to a new query</span></span>  
  
1.  <span data-ttu-id="e4e01-115">Убедитесь в том, что для создаваемого запроса отображается **панель SQL** .</span><span class="sxs-lookup"><span data-stu-id="e4e01-115">Make sure the **SQL Pane** is displayed in the new query you are creating.</span></span>  
  
2.  <span data-ttu-id="e4e01-116">Введите на **панели SQL**после слова FROM левую и правую скобки ().</span><span class="sxs-lookup"><span data-stu-id="e4e01-116">In the **SQL Pane**, type a right and left parentheses () after the word FROM.</span></span>  
  
3.  <span data-ttu-id="e4e01-117">Откройте для существующего запроса конструктор запросов</span><span class="sxs-lookup"><span data-stu-id="e4e01-117">Open the Query Designer for the existing query.</span></span> <span data-ttu-id="e4e01-118">(теперь должны быть открыты два конструктора запросов).</span><span class="sxs-lookup"><span data-stu-id="e4e01-118">(You now have two Query Designers open.)</span></span>  
  
4.  <span data-ttu-id="e4e01-119">Отобразите **панель SQL** для внутреннего запроса, то есть существующего запроса, который включается в новый, внешний запрос.</span><span class="sxs-lookup"><span data-stu-id="e4e01-119">Display the **SQL Pane** for the inner query - the existing query you are including in the new, outer query.</span></span>  
  
5.  <span data-ttu-id="e4e01-120">Выделите весь текст на **панели SQL**и скопируйте его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="e4e01-120">Select all the text in the **SQL Pane**, and copy it to the Clipboard.</span></span>  
  
6.  <span data-ttu-id="e4e01-121">Щелкните **панель SQL** нового запроса, установите курсор между добавленными скобками и вставьте в них содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="e4e01-121">Click in the **SQL Pane** of the new query, situate the cursor between the parentheses you added, and paste the contents of the Clipboard.</span></span>  
  
7.  <span data-ttu-id="e4e01-122">Продолжая работать на **панели SQL**, укажите псевдоним после правой скобки.</span><span class="sxs-lookup"><span data-stu-id="e4e01-122">Still in the **SQL Pane**, add an alias after the right parenthesis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e01-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="e4e01-123">See Also</span></span>  
 <span data-ttu-id="e4e01-124">[Создание псевдонимов таблиц &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e4e01-124">[Create Table Aliases &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="e4e01-125">[Удаление таблиц из запросов &#40;визуальных инструментов для баз данных&#41;](remove-tables-from-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e4e01-125">[Remove Tables from Queries &#40;Visual Database Tools&#41;](remove-tables-from-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="e4e01-126">[Укажите условия поиска &#40;визуальные инструменты для баз данных&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e4e01-126">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="e4e01-127">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e4e01-127">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e4e01-128">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e4e01-128">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
