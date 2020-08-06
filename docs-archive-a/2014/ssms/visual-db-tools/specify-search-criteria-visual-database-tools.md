---
title: Определение критериев поиска (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Query Designer [SQL Server], Criteria pane
- queries [Visual Database Tools]
- criteria for search conditions
- search conditions [SQL Server], search criteria
- View Designer, Criteria pane
- row return limitations [SQL Server]
- Criteria pane
- restricting rows returned
- search criteria [SQL Server]
- Visual Database Tools [SQL Server], queries
- limiting rows returned
ms.assetid: 25fb4e31-6dbf-4cf6-8e47-0dd0998c836c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 258aceb348ed3bcd7d4d19201a0169b53b54d711
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659064"
---
# <a name="specify-search-criteria-visual-database-tools"></a><span data-ttu-id="7bb60-102">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-102">Specify Search Criteria (Visual Database Tools)</span></span>
  <span data-ttu-id="7bb60-103">Чтобы ограничить количество возвращаемых по запросу строк, можно использовать критерии поиска.</span><span class="sxs-lookup"><span data-stu-id="7bb60-103">You can use search criteria to restrict the number of rows returned by a query.</span></span>  
  
 <span data-ttu-id="7bb60-104">Дополнительные сведения о создании критерия поиска приведены в подразделах, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7bb60-104">For details about the particular steps to creating search criteria, refer to the topics listed in the following table.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7bb60-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7bb60-105">In This Section</span></span>  
 [<span data-ttu-id="7bb60-106">Правила ввода значений для поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-106">Rules for Entering Search Values &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
 <span data-ttu-id="7bb60-107">Разъясняется, как вводить текст, числа, даты и логические значения.</span><span class="sxs-lookup"><span data-stu-id="7bb60-107">Explains how to enter text, numbers, dates, or logical values.</span></span>  
  
 [<span data-ttu-id="7bb60-108">Обозначения для условий комбинированного поиска на панели критериев (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-108">Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;</span></span>](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
 <span data-ttu-id="7bb60-109">Объясняются принципы использования операторов AND и OR.</span><span class="sxs-lookup"><span data-stu-id="7bb60-109">Explains the concepts behind using the AND and OR operators.</span></span>  
  
 [<span data-ttu-id="7bb60-110">Указание условий поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-110">Specify Search Conditions &#40;Visual Database Tools&#41;</span></span>](specify-search-conditions-visual-database-tools.md)  
 <span data-ttu-id="7bb60-111">Объясняются принципы выбора критерия поиска, обеспечивающего извлечение только необходимых данных.</span><span class="sxs-lookup"><span data-stu-id="7bb60-111">Explains the basics of choosing search criteria to get just the data you want.</span></span>  
  
 [<span data-ttu-id="7bb60-112">Указание нескольких условий поиска для одного столбца (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-112">Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-one-column-visual-database-tools.md)  
 <span data-ttu-id="7bb60-113">Объясняется, как создавать несколько условий поиска для одного столбца данных.</span><span class="sxs-lookup"><span data-stu-id="7bb60-113">Explains how to create multiple search conditions to the same data column.</span></span>  
  
 [<span data-ttu-id="7bb60-114">Указание нескольких условий поиска для нескольких столбцов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-114">Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md)  
 <span data-ttu-id="7bb60-115">Объясняется, как включать несколько столбцов данных в условие поиска для запроса.</span><span class="sxs-lookup"><span data-stu-id="7bb60-115">Explains how to include several data columns as part of the search condition for a query.</span></span>  
  
 [<span data-ttu-id="7bb60-116">Указание предложения TOP в запросах (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-116">Specify the TOP Clause in Queries &#40;Visual Database Tools&#41;</span></span>](specify-the-top-clause-in-queries-visual-database-tools.md)  
 <span data-ttu-id="7bb60-117">Объясняется, как задать количество или процентное соотношение возвращаемых строк.</span><span class="sxs-lookup"><span data-stu-id="7bb60-117">Explains how to have only a given number or percentage of rows returned.</span></span>  
  
 [<span data-ttu-id="7bb60-118">Использование предложения HAVING и WHERE в одном запросе (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-118">Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;</span></span>](use-having-and-where-clauses-in-the-same-query-visual-database-tools.md)  
 <span data-ttu-id="7bb60-119">Объясняется, как и для чего используются оба представленных предложения в запросе.</span><span class="sxs-lookup"><span data-stu-id="7bb60-119">Explains how and why to use both of these clauses in a query.</span></span>  
  
 [<span data-ttu-id="7bb60-120">Выбор строк, не соответствующих заданному значению (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-120">Select Rows That Do Not Match a Value &#40;Visual Database Tools&#41;</span></span>](select-rows-that-do-not-match-a-value-visual-database-tools.md)  
 <span data-ttu-id="7bb60-121">Объясняется, как настроить подачу выходной информации таким образом, чтобы в ней не содержалось строк, в которых имеется значение, заданное в инструкции запроса.</span><span class="sxs-lookup"><span data-stu-id="7bb60-121">Explains how to return all rows where the value of a give column does not match the value you provide in the query statement.</span></span>  
  
 [<span data-ttu-id="7bb60-122">Включение или исключение строк (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-122">Include or Exclude Rows &#40;Visual Database Tools&#41;</span></span>](include-or-exclude-rows-visual-database-tools.md)  
 <span data-ttu-id="7bb60-123">Объясняются принципы использования предложений и операторов в запросах.</span><span class="sxs-lookup"><span data-stu-id="7bb60-123">Explains the concepts behind clauses and operators used in queries.</span></span>  
  
 [<span data-ttu-id="7bb60-124">Исключение повторяющихся строк (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-124">Exclude Duplicate Rows &#40;Visual Database Tools&#41;</span></span>](exclude-duplicate-rows-visual-database-tools.md)  
 <span data-ttu-id="7bb60-125">Объясняется, как исключить из запросов SELECT повторяющиеся строки.</span><span class="sxs-lookup"><span data-stu-id="7bb60-125">Explains how to filter duplicate rows out of Select queries.</span></span>  
  
 [<span data-ttu-id="7bb60-126">Объединение условий, если приоритет имеет оператор AND (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-126">Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
 <span data-ttu-id="7bb60-127">Объясняется, как и для чего используется оператор AND при фильтрации результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="7bb60-127">Explains why and how to use the AND operator to filter query results.</span></span>  
  
 [<span data-ttu-id="7bb60-128">Соединение условий, если приоритет имеет оператор OR (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-128">Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
 <span data-ttu-id="7bb60-129">Объясняется, как и для чего используется оператор OR при фильтрации результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="7bb60-129">Explains why and how to use the OR operator to filter query results.</span></span>  
  
 [<span data-ttu-id="7bb60-130">Создание вложенных запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-130">Create Subqueries &#40;Visual Database Tools&#41;</span></span>](create-subqueries-visual-database-tools.md)  
 <span data-ttu-id="7bb60-131">Объясняется, как создавать вложенные запросы или запросы более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="7bb60-131">Explains how to create subqueries, or nested queries.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7bb60-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7bb60-132">Related Sections</span></span>  
 [<span data-ttu-id="7bb60-133">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-133">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
 <span data-ttu-id="7bb60-134">Содержит ссылки на подразделы, в которых приводятся пошаговые инструкции по выполнению самых общих задач с запросами.</span><span class="sxs-lookup"><span data-stu-id="7bb60-134">Provides links to topics with steps for the most common querying tasks.</span></span>  
  
 [<span data-ttu-id="7bb60-135">Типы запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-135">Types of Queries &#40;Visual Database Tools&#41;</span></span>](types-of-queries-visual-database-tools.md)  
 <span data-ttu-id="7bb60-136">Содержит ссылки на подразделы, в которых перечисляются поддерживаемые типы запросов.</span><span class="sxs-lookup"><span data-stu-id="7bb60-136">Provides links to topics explaining the supported query types.</span></span>  
  
 [<span data-ttu-id="7bb60-137">Результаты запросов сортировки и группирования (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-137">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
 <span data-ttu-id="7bb60-138">Содержит ссылки на подразделы, в которых приводятся пошаговые инструкции по выполнению сортировки и группировки результатов запроса.</span><span class="sxs-lookup"><span data-stu-id="7bb60-138">Provides links to topics with steps for sorting and grouping the results of a query.</span></span>  
  
 [<span data-ttu-id="7bb60-139">Резюмирование результатов запросов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-139">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
 <span data-ttu-id="7bb60-140">Содержит ссылки на подразделы, в которых приводятся пошаговые инструкции по выполнению анализа результатов запроса, включая столбцы с пустыми и нечисловыми значениями.</span><span class="sxs-lookup"><span data-stu-id="7bb60-140">Provides links to topics with steps for summarizing results, including NULL and Nonnumeric columns.</span></span>  
  
 [<span data-ttu-id="7bb60-141">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7bb60-141">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
 <span data-ttu-id="7bb60-142">Содержит ссылки на подразделы, в которых описываются возможные действия над запросами и представлениями при использовании соответствующих конструкторов.</span><span class="sxs-lookup"><span data-stu-id="7bb60-142">Provides links to topics and sections covering work you can do in queries and views using the Query and View Designer.</span></span>  
  
  
