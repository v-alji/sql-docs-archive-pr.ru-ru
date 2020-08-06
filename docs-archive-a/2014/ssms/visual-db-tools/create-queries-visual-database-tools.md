---
title: Создание запросов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], creating
ms.assetid: 696a080d-848f-44d3-a918-e29bafaab85a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52392adff03b27e1c4c19f354bc62c350cccf17a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654713"
---
# <a name="create-queries-visual-database-tools"></a><span data-ttu-id="1cd76-102">Создание запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="1cd76-102">Create Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="1cd76-103">Запросы позволяют получить данные из таблиц и представлений базы данных.</span><span class="sxs-lookup"><span data-stu-id="1cd76-103">Queries allow you to retrieve data from the tables and views in your database.</span></span> <span data-ttu-id="1cd76-104">Для создания запросов и работы с ними служит **Конструктор запросов и представлений**, который содержит четыре панели: [панель диаграммы](visual-database-tools.md), [панель SQL](sql-pane-visual-database-tools.md), [панель критериев](criteria-pane-visual-database-tools.md)и [панель результатов](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1cd76-104">You create and work with queries in **Query and View Designer**, which is composed of four panes: the [Diagram Pane](visual-database-tools.md), the [SQL Pane](sql-pane-visual-database-tools.md), the [Criteria Pane](criteria-pane-visual-database-tools.md), and the [Results Pane](results-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-a-new-query"></a><span data-ttu-id="1cd76-105">Создание нового запроса</span><span class="sxs-lookup"><span data-stu-id="1cd76-105">To create a new query</span></span>  
  
1.  <span data-ttu-id="1cd76-106">В **обозревателе объектов**разверните узел **Таблицы** для запрашиваемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="1cd76-106">In **Object Explorer**, expand the **Tables** node for the database you want to query.</span></span> <span data-ttu-id="1cd76-107">Щелкните нужную таблицу правой кнопкой мыши и выберите пункт **Открыть таблицу**.</span><span class="sxs-lookup"><span data-stu-id="1cd76-107">Right-click the table you want to query and click **Open Table**.</span></span>  
  
2.  <span data-ttu-id="1cd76-108">Если в запрос нужно добавить еще какие-нибудь таблицы, в меню конструктора запросов выберите пункт **Добавить таблицу**.</span><span class="sxs-lookup"><span data-stu-id="1cd76-108">To add more tables to the query, on the Query Designer menu, select **Add Table**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1cd76-109">Если панели **Диаграмма**, **SQL**, **Критерии**или **Результаты** отсутствуют, в меню конструктора запросов выберите **Область** и щелкните панель, которую нужно открыть.</span><span class="sxs-lookup"><span data-stu-id="1cd76-109">If you do not see the **Diagram**, **SQL**, **Criteria**, or **Results** panes, from the Query Designer menu, point to **Pane** and click the pane you want to open.</span></span>  
  
3.  <span data-ttu-id="1cd76-110">В диалоговом окне **Добавление таблицы** выберите таблицы, к которым будет обращаться запрос, и для каждой из них нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="1cd76-110">In the **Add Table** dialog box, select the tables you want to query and click **Add** for each one.</span></span>  
  
4.  <span data-ttu-id="1cd76-111">Выбрав нужные таблицы, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1cd76-111">Once you have added all the tables you want to query, click **Close**.</span></span>  
  
     <span data-ttu-id="1cd76-112">Чтобы добавить новые таблицы, щелкните открытое место на панели **Диаграмма** правой кнопкой мыши и из контекстного меню выберите **Добавить таблицу**.</span><span class="sxs-lookup"><span data-stu-id="1cd76-112">To add more tables later, right-click the open space in the **Diagram** pane and from the shortcut menu click **Add Table**.</span></span>  
  
5.  <span data-ttu-id="1cd76-113">На **панели диаграммы**установите флажки в возвращающих табличное значение объектах для каждого столбца, к которому обращается запрос.</span><span class="sxs-lookup"><span data-stu-id="1cd76-113">In the **Diagram Pane**, check the boxes in the table-valued objects for each column you want to query.</span></span>  
  
6.  <span data-ttu-id="1cd76-114">Чтобы выполнить запрос, в меню конструктора запросов выберите **Выполнить SQL** .</span><span class="sxs-lookup"><span data-stu-id="1cd76-114">From the Query Designer menu, choose **Execute SQL** to run your query.</span></span>  
  
 <span data-ttu-id="1cd76-115">При дальнейшем улучшении запроса можно изменить код SQL на **панели SQL** или выбрать такие параметры, как порядок сортировки или псевдонимы столбцов на **панели критериев**.</span><span class="sxs-lookup"><span data-stu-id="1cd76-115">To further refine your query, you can change the SQL code in the **SQL Pane** or choose options such as sort order and column aliases in the **Criteria Pane.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd76-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="1cd76-116">See Also</span></span>  
 <span data-ttu-id="1cd76-117">[Сохранение запросов &#40;визуальных инструментов для баз данных&#41;](save-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1cd76-117">[Save Queries &#40;Visual Database Tools&#41;](save-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="1cd76-118">[Типы запросов &#40;визуальных инструментов для баз данных&#41;](types-of-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1cd76-118">[Types of Queries &#40;Visual Database Tools&#41;](types-of-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="1cd76-119">[Укажите условия поиска &#40;визуальные инструменты для баз данных&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1cd76-119">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 <span data-ttu-id="1cd76-120">[Суммировать результаты запроса &#40;визуальных инструментов для баз данных&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1cd76-120">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1cd76-121">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="1cd76-121">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
