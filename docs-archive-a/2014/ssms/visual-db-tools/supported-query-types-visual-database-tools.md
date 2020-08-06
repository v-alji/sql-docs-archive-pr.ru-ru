---
title: Поддерживаемые типы запросов (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Delete query
- queries [SQL Server], types
- Update query
- Query Designer [SQL Server], query types
- Criteria pane
- Insert Values query
- Select query
- Make Table query
- Insert Results query
- Diagram pane [Visual Database Tools]
- View Designer, query types
ms.assetid: 72b9116c-c128-4078-a78d-257a2955a3f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b00b7018fc6d0b631696811bd1870e09842b4162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735782"
---
# <a name="supported-query-types-visual-database-tools"></a><span data-ttu-id="25495-102">Поддерживаемые типы запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="25495-102">Supported Query Types (Visual Database Tools)</span></span>
  <span data-ttu-id="25495-103">На панелях диаграммы и критериев (графические области) [конструктора запросов и представлений](visual-database-tools.md)можно создать запросы следующих типов:</span><span class="sxs-lookup"><span data-stu-id="25495-103">You can create the following types of queries in the Diagram and Criteria panes (the graphical panes) of the [Query and View Designer](visual-database-tools.md):</span></span>  
  
-   <span data-ttu-id="25495-104">**Запрос SELECT** . Получает данные из одной или нескольких таблиц или представлений.</span><span class="sxs-lookup"><span data-stu-id="25495-104">**Select query** Retrieves data from one or more tables or views.</span></span> <span data-ttu-id="25495-105">Запрос этого типа создает инструкцию SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="25495-105">This type of query creates an SQL SELECT statement.</span></span>  
  
-   <span data-ttu-id="25495-106">**Вставить результаты** . Создает новые строки копированием существующих строк из одной таблицы в другую или в ту же самую таблицу в качестве новых строк.</span><span class="sxs-lookup"><span data-stu-id="25495-106">**Insert Results** Creates new rows by copying existing rows from one table into another, or into the same table as new rows.</span></span> <span data-ttu-id="25495-107">Запрос этого типа создает инструкцию SQL INSERT INTO...SELECT.</span><span class="sxs-lookup"><span data-stu-id="25495-107">This type of query creates an SQL INSERT INTO...SELECT statement.</span></span>  
  
-   <span data-ttu-id="25495-108">**Вставить значения** . Создает новую строку и вставляет значения в заданные столбцы.</span><span class="sxs-lookup"><span data-stu-id="25495-108">**Insert Values** Creates a new row and inserts values into specified columns.</span></span> <span data-ttu-id="25495-109">Запрос этого типа создает инструкцию SQL INSERT INTO...VALUES.</span><span class="sxs-lookup"><span data-stu-id="25495-109">This type of query creates an SQL INSERT INTO...VALUES statement.</span></span>  
  
-   <span data-ttu-id="25495-110">**Запрос на обновление** . Изменяет значения отдельных столбцов в одной или нескольких существующих строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="25495-110">**Update query** Changes the values of individual columns in one or more existing rows in a table.</span></span> <span data-ttu-id="25495-111">Запрос этого типа создает инструкцию SQL UPDATE...SET.</span><span class="sxs-lookup"><span data-stu-id="25495-111">This type of query creates an SQL UPDATE...SET statement.</span></span>  
  
-   <span data-ttu-id="25495-112">**Запрос на удаление** . Удаляет одну или несколько строк из таблицы.</span><span class="sxs-lookup"><span data-stu-id="25495-112">**Delete query** Removes one or more rows from a table.</span></span> <span data-ttu-id="25495-113">Запрос этого типа создает инструкцию SQL DELETE.</span><span class="sxs-lookup"><span data-stu-id="25495-113">This type of query creates an SQL DELETE statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25495-114">Запрос «Удаление» удаляет строки из таблицы целиком.</span><span class="sxs-lookup"><span data-stu-id="25495-114">A Delete query removes entire rows from the table.</span></span> <span data-ttu-id="25495-115">Если необходимо удалить значения из отдельных столбцов данных, используйте запрос «Обновление».</span><span class="sxs-lookup"><span data-stu-id="25495-115">If you want to delete values from individual data columns, use an Update query.</span></span>  
  
-   <span data-ttu-id="25495-116">**Запрос на создание таблицы** . Создает новую таблицу и строки в этой таблице, копируя в нее результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="25495-116">**Make Table query** Creates a new table and creates rows in it by copying the results of a query into it.</span></span> <span data-ttu-id="25495-117">Запрос этого типа создает инструкцию SQL SELECT...INTO.</span><span class="sxs-lookup"><span data-stu-id="25495-117">This type of query creates an SQL SELECT...INTO statement.</span></span>  
  
 <span data-ttu-id="25495-118">В дополнение к этим запросам, создаваемым при помощи графических панелей, на панель SQL можно ввести любую инструкцию SQL, например запросы объединения.</span><span class="sxs-lookup"><span data-stu-id="25495-118">In addition to the queries you can create using the graphical panes, you can enter any SQL statement into the SQL pane, such as Union queries.</span></span>  
  
 <span data-ttu-id="25495-119">При создании запросов при помощи инструкций SQL, которые не могут быть представлены на графических панелях, конструктор запросов и представлений затемняет эти панели, указывая тем самым, что они не отражают создаваемый вами запрос.</span><span class="sxs-lookup"><span data-stu-id="25495-119">When you create queries using SQL statements that cannot be represented in the graphical panes, the Query and View Designer dims those panes to indicate that they do not reflect the query you are creating.</span></span> <span data-ttu-id="25495-120">Однако затемненные панели остаются активными, и во многих случаях на этих панелях можно производить изменения запросов.</span><span class="sxs-lookup"><span data-stu-id="25495-120">However, the dimmed panes are still active and, in many cases, you can make changes to the query in those panes.</span></span> <span data-ttu-id="25495-121">Если выполняемые изменения приводят к запросу, который может быть представлен на графических панелях, эти панели перестают затемняться.</span><span class="sxs-lookup"><span data-stu-id="25495-121">If the changes you make result in a query that can be represented in the graphical panes, those panes are no longer dimmed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25495-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="25495-122">See Also</span></span>  
 <span data-ttu-id="25495-123">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="25495-123">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="25495-124">Типы запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="25495-124">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
  
  
