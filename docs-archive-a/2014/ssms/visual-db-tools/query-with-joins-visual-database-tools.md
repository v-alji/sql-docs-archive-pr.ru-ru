---
title: Запросы с соединениями (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [Visual Database Tools]
- View Designer, joins
- table joins [SQL Server]
- multiple table joins
- Visual Database Tools [SQL Server], queries
- Query Designer [SQL Server], joins
- joins [SQL Server], queries
ms.assetid: 8f068207-d777-4e64-8c4c-d821f0ddb450
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9d0053e6786d96508be8a87347cdc0b19975a3fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729993"
---
# <a name="query-with-joins-visual-database-tools"></a><span data-ttu-id="518f8-102">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-102">Query with Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="518f8-103">Результат запроса может содержать данные из нескольких таблиц или табличных объектов.</span><span class="sxs-lookup"><span data-stu-id="518f8-103">A query result can include data from multiple tables or table-valued objects.</span></span> <span data-ttu-id="518f8-104">Чтобы соединить данные из нескольких возвращающих табличное значение объектов, используется оператор SQL JOIN.</span><span class="sxs-lookup"><span data-stu-id="518f8-104">To combine data from multiple table-valued objects, you use the JOIN operation from SQL.</span></span>  
  
 <span data-ttu-id="518f8-105">Сведения о создании запросов с использованием нескольких таблиц см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="518f8-105">For information about creating queries using multiple tables, see the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="518f8-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="518f8-106">In This Section</span></span>  
 [<span data-ttu-id="518f8-107">Изменение операторов соединения (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-107">Modify Join Operators &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
 <span data-ttu-id="518f8-108">Заметим, что таблицы не могут быть соединены с помощью оператора «равно» (=).</span><span class="sxs-lookup"><span data-stu-id="518f8-108">Specify that tables should be joined using an operator other than equal (=).</span></span>  
  
 [<span data-ttu-id="518f8-109">Как конструктор запросов и представлений представляет соединения (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-109">How the Query and View Designer Represents Joins &#40;Visual Database Tools&#41;</span></span>](how-the-query-and-view-designer-represents-joins-visual-database-tools.md)  
 <span data-ttu-id="518f8-110">Поясняет графическое представление соединения, отображенное на панели диаграмм.</span><span class="sxs-lookup"><span data-stu-id="518f8-110">Explains the graphic representation of the join as you see it in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="518f8-111">Автоматическое соединение таблиц (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-111">Join Tables Automatically &#40;Visual Database Tools&#41;</span></span>](join-tables-automatically-visual-database-tools.md)  
 <span data-ttu-id="518f8-112">Действия, позволяющие конструкторам запросов и представлений определять необходимость соединения таблиц.</span><span class="sxs-lookup"><span data-stu-id="518f8-112">Steps for allowing the Query and View Designer determine if tables should be joined.</span></span>  
  
 [<span data-ttu-id="518f8-113">Соединение таблиц вручную (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-113">Join Tables Manually &#40;Visual Database Tools&#41;</span></span>](join-tables-manually-visual-database-tools.md)  
 <span data-ttu-id="518f8-114">Действия для создания соединения на панели диаграмм вручную.</span><span class="sxs-lookup"><span data-stu-id="518f8-114">Steps for creating a join manually in the Diagram pane.</span></span>  
  
 [<span data-ttu-id="518f8-115">Соединение таблиц по нескольким столбцам (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-115">Join Tables on Multiple Columns &#40;Visual Database Tools&#41;</span></span>](join-tables-on-multiple-columns-visual-database-tools.md)  
 <span data-ttu-id="518f8-116">Действия по соединению таблиц с несколькими критериями для каждой таблицы.</span><span class="sxs-lookup"><span data-stu-id="518f8-116">Steps for joining tables with multiple criteria for each table.</span></span>  
  
 [<span data-ttu-id="518f8-117">Создание внешних соединений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-117">Create Outer Joins &#40;Visual Database Tools&#41;</span></span>](create-outer-joins-visual-database-tools.md)  
 <span data-ttu-id="518f8-118">Указывает на то, что при соединении таблиц несовпадающие строки не удаляются.</span><span class="sxs-lookup"><span data-stu-id="518f8-118">Specify that joined tables should include rows even when they do not match rows in the corresponding table.</span></span>  
  
 [<span data-ttu-id="518f8-119">Удаление соединений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-119">Remove Joins &#40;Visual Database Tools&#41;</span></span>](remove-joins-visual-database-tools.md)  
 <span data-ttu-id="518f8-120">Действия для удаления соединения между таблицами.</span><span class="sxs-lookup"><span data-stu-id="518f8-120">Steps for removing a join between tables.</span></span>  
  
 [<span data-ttu-id="518f8-121">Автоматическое создание самосоединения (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-121">Create Self-Joins Automatically &#40;Visual Database Tools&#41;</span></span>](create-self-joins-automatically-visual-database-tools.md)  
 <span data-ttu-id="518f8-122">Действия, позволяющие конструкторам запросов и представлений создавать самосоединения.</span><span class="sxs-lookup"><span data-stu-id="518f8-122">Steps for allowing the Query and View Designer to create a self-join.</span></span>  
  
 [<span data-ttu-id="518f8-123">Создание самосоединения вручную (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-123">Create Self-Joins Manually &#40;Visual Database Tools&#41;</span></span>](create-self-joins-manually-visual-database-tools.md)  
 <span data-ttu-id="518f8-124">Действия, позволяющие использовать соединение для обнаружения подмножеств данных внутри одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="518f8-124">Steps for using a join to find subsets of data within a single table.</span></span>  
  
 [<span data-ttu-id="518f8-125">Просмотр свойств соединения (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-125">View Join Properties &#40;Visual Database Tools&#41;</span></span>](view-join-properties-visual-database-tools.md)  
 <span data-ttu-id="518f8-126">Действия для просмотра свойств соединения.</span><span class="sxs-lookup"><span data-stu-id="518f8-126">Steps for viewing the properties of a join.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="518f8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="518f8-127">Related Sections</span></span>  
 [<span data-ttu-id="518f8-128">Типы запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-128">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
 <span data-ttu-id="518f8-129">Содержит ссылки на разделы, в которых перечисляются поддерживаемые типы запросов.</span><span class="sxs-lookup"><span data-stu-id="518f8-129">Provides links to topics describing the supported query types.</span></span>  
  
 [<span data-ttu-id="518f8-130">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
 <span data-ttu-id="518f8-131">Ссылки на подразделы о самых общих задачах запросов.</span><span class="sxs-lookup"><span data-stu-id="518f8-131">Provides links to topics covering the most common query tasks.</span></span>  
  
 [<span data-ttu-id="518f8-132">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="518f8-132">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
 <span data-ttu-id="518f8-133">Содержит ссылки на разделы, в которых перечисляются различные типы критериев поиска и рассказывается об их применении.</span><span class="sxs-lookup"><span data-stu-id="518f8-133">Provides links to topics covering the various kinds of search criteria and how to use them.</span></span>  
  
  
