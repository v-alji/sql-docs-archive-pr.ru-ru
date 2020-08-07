---
title: Соглашения для комбинирования условий поиска на панели критериев (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- multiple OR clauses
- combining search conditions
- OR operator
- AND, Criteria pane
- multiple AND clauses
ms.assetid: d4859be5-ff5b-48b2-a101-ad40c6dbcc68
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684521baa87d5325366a0e18296cd35342a0e947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727806"
---
# <a name="conventions-for-combining-search-conditions-in-the-criteria-pane-visual-database-tools"></a><span data-ttu-id="d8330-102">Обозначения для условий комбинированного поиска на панели критериев (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d8330-102">Conventions for Combining Search Conditions in the Criteria Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="d8330-103">Предусмотрена возможность создания запросов, включающих любое количество условий поиска, соединенных любым количеством операторов AND и OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-103">You can create queries that include any number of search conditions, linked with any number of AND and OR operators.</span></span> <span data-ttu-id="d8330-104">Запрос с сочетанием предложений AND и OR может стать сложным, поэтому важно знать, как такой запрос интерпретируется при выполнении и представляется на [панели критериев](visual-database-tools.md) и [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d8330-104">A query with a combination of AND and OR clauses can become complex, so it is helpful to understand how such a query is interpreted when you execute it, and how such a query is represented in the [Criteria Pane](visual-database-tools.md) and [SQL Pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8330-105">Дополнительные сведения об условиях поиска, которые содержат только один оператор AND или OR, см. в разделах [Указание нескольких условий поиска для одного столбца (визуальные инструменты для баз данных)](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) и [Указание нескольких условий поиска для нескольких столбцов (визуальные инструменты для баз данных)](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d8330-105">For details about search conditions that contain only one AND or OR operator, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) and [Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="d8330-106">Ниже содержатся сведения о следующем:</span><span class="sxs-lookup"><span data-stu-id="d8330-106">Below you will find information about:</span></span>  
  
-   <span data-ttu-id="d8330-107">Приоритет AND и OR в запросах, содержащих их оба.</span><span class="sxs-lookup"><span data-stu-id="d8330-107">The precedence of AND and OR in queries that contain both.</span></span>  
  
-   <span data-ttu-id="d8330-108">Как условия в предложениях AND и OR логически связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d8330-108">How the conditions in AND and OR clauses relate logically to one another.</span></span>  
  
-   <span data-ttu-id="d8330-109">Как конструктор запросов и представлений отображает на панели критериев запросы, содержащие AND и OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-109">How the Query and View Designer represents in the Criteria Pane queries that contain both AND and OR.</span></span>  
  
 <span data-ttu-id="d8330-110">Для простоты понимания нижеследующего представьте, что работаете с таблицей `employee` , содержащей столбцы `hire_date`, `job_lvl`и `status`.</span><span class="sxs-lookup"><span data-stu-id="d8330-110">To help you understand the discussion below, imagine that you are working with an `employee` table containing the columns `hire_date`, `job_lvl`, and `status`.</span></span> <span data-ttu-id="d8330-111">В примерах предполагается, что пользователи должны знать такие сведения, как дата найма сотрудника, какой вид работы он выполняет (его должность), а также его состояние (например, уволенный).</span><span class="sxs-lookup"><span data-stu-id="d8330-111">The examples assume that you need to know information such as how long an employee has worked with the company (that is, what the employee's hire date is), what type of job the employee performs (what the job level is), and the employee's status (for example, retired).</span></span>  
  
## <a name="precedence-of-and-and-or"></a><span data-ttu-id="d8330-112">Приоритет AND и OR</span><span class="sxs-lookup"><span data-stu-id="d8330-112">Precedence of AND and OR</span></span>  
 <span data-ttu-id="d8330-113">При выполнении запроса сначала проверяются предложения, соединенные AND, а затем — соединенные OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-113">When a query is executed, it evaluates first the clauses linked with AND, and then those linked with OR.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8330-114">Оператор NOT имеет приоритет над AND и над OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-114">The NOT operator takes precedence over both AND and OR.</span></span>  
  
 <span data-ttu-id="d8330-115">Например, чтобы найти либо сотрудников, которые проработали в компании более пяти лет на младших должностях, либо сотрудников среднего звена безотносительно к дате найма, можно сконструировать следующее предложение WHERE:</span><span class="sxs-lookup"><span data-stu-id="d8330-115">For example, to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs without regard for their hire date, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   job_lvl = 100 OR  
   job_lvl = 200  
  
```  
  
 <span data-ttu-id="d8330-116">Для переопределения приоритета AND над OR, используемого по умолчанию, можно поместить определенные условия на панели SQL в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="d8330-116">To override the default precedence of AND over OR, you can put parentheses around specific conditions in the SQL pane.</span></span> <span data-ttu-id="d8330-117">Условия в круглых скобках всегда вычисляются первыми.</span><span class="sxs-lookup"><span data-stu-id="d8330-117">Conditions in parentheses are always evaluated first.</span></span> <span data-ttu-id="d8330-118">Например, чтобы найти всех сотрудников, которые проработали в компании на младших или средних должностях более пяти лет, можно сконструировать следующее предложение WHERE:</span><span class="sxs-lookup"><span data-stu-id="d8330-118">For example, to find all employees who have been with the company more than five years in either lower or middle-level jobs, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
> [!TIP]  
>  <span data-ttu-id="d8330-119">Рекомендуется для ясности всегда задавать круглые скобки при сочетании предложений AND и OR вместо использования приоритета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8330-119">It is recommended that, for clarity, you always include parentheses when combining AND and OR clauses instead of relying on the default precedence.</span></span>  
  
## <a name="how-and-works-with-multiple-or-clauses"></a><span data-ttu-id="d8330-120">Работа AND с несколькими предложениями OR</span><span class="sxs-lookup"><span data-stu-id="d8330-120">How AND Works with Multiple OR Clauses</span></span>  
 <span data-ttu-id="d8330-121">Понимание того, как работают предложения AND и OR при объединении, поможет при составлении и изучении сложных запросов в конструкторе запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="d8330-121">Understanding how AND and OR clauses are related when combined can help you construct and understand complex queries in the Query and View Designer.</span></span>  
  
 <span data-ttu-id="d8330-122">При соединении нескольких условий с помощью AND первый набор условий, соединенных AND, применяется ко всем условиям из второго набора.</span><span class="sxs-lookup"><span data-stu-id="d8330-122">If you link multiple conditions using AND, the first set of conditions linked with AND applies to all the conditions in the second set.</span></span> <span data-ttu-id="d8330-123">Другими словами, условие, соединенное AND с другим условием, распространяется на все условия второго набора.</span><span class="sxs-lookup"><span data-stu-id="d8330-123">In other words, a condition linked with AND to another condition is distributed to all the conditions in the second set.</span></span> <span data-ttu-id="d8330-124">Например, следующее схематичное представление иллюстрирует условие AND, соединенное с набором условий OR:</span><span class="sxs-lookup"><span data-stu-id="d8330-124">For example, the following schematic representation shows an AND condition linked to a set of OR conditions:</span></span>  
  
```  
A AND (B OR C)  
```  
  
 <span data-ttu-id="d8330-125">Вышеприведенное представление логически идентично следующему схематичному представлению, иллюстрирующему распространение условия AND на второй набор условий:</span><span class="sxs-lookup"><span data-stu-id="d8330-125">The representation above is logically equivalent to the following schematic representation, which shows how the AND condition is distributed to the second set of conditions:</span></span>  
  
```  
(A AND B) OR (A AND C)  
```  
  
 <span data-ttu-id="d8330-126">Этот принцип распространения влияет на использование конструктора запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="d8330-126">This distributive principle affects how you use the Query and View Designer.</span></span> <span data-ttu-id="d8330-127">Например, пользователь ищет всех сотрудников, работающих в компании более пяти лет на младших или средних должностях.</span><span class="sxs-lookup"><span data-stu-id="d8330-127">For example, imagine that you are looking for all employees who have been with the company more than five years in either lower or middle-level jobs.</span></span> <span data-ttu-id="d8330-128">Следующее предложение WHERE добавляется в инструкцию на панели SQL:</span><span class="sxs-lookup"><span data-stu-id="d8330-128">You enter the following WHERE clause into the statement in the SQL pane:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
 <span data-ttu-id="d8330-129">Предложение, соединенное AND, применяется к обоим предложениям, соединенным OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-129">The clause linked with AND applies to both clauses linked with OR.</span></span> <span data-ttu-id="d8330-130">Явно это можно выразить посредством повторения условия AND по одному разу для каждого условия в предложении OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-130">An explicit way to express this is to repeat the AND condition once for each condition in the OR clause.</span></span> <span data-ttu-id="d8330-131">Следующая инструкция более точная (и длинная), чем предыдущая, но логически идентична ей:</span><span class="sxs-lookup"><span data-stu-id="d8330-131">The following statement is more explicit (and longer) than the previous statement, but is logically equivalent to it:</span></span>  
  
```  
WHERE    (hire_date < '01/01/95' ) AND  
  (job_lvl = 100) OR   
  (hire_date < '01/01/95' ) AND   
  (job_lvl = 200)  
```  
  
 <span data-ttu-id="d8330-132">Принцип распространения предложений AND на соединенные предложения OR применяется вне зависимости от количества отдельных учитываемых условий.</span><span class="sxs-lookup"><span data-stu-id="d8330-132">The principle of distributing AND clauses to linked OR clauses applies no matter how many individual conditions are involved.</span></span> <span data-ttu-id="d8330-133">Например, пусть требуется найти сотрудников высокого или среднего звена, проработавших в компании более пяти лет либо уволенных.</span><span class="sxs-lookup"><span data-stu-id="d8330-133">For example, imagine that you want to find higher or middle-level employees who have been with the company more than five years or are retired.</span></span> <span data-ttu-id="d8330-134">Предложение WHERE может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="d8330-134">The WHERE clause might look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 OR job_lvl = 300) AND  
   (hire_date < '01/01/95' ) OR (status = 'R')  
```  
  
 <span data-ttu-id="d8330-135">После распространения условий, соединенных AND, предложение WHERE выглядит так:</span><span class="sxs-lookup"><span data-stu-id="d8330-135">After the conditions linked with AND have been distributed, the WHERE clause will look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 200 AND status = 'R') OR  
   (job_lvl = 300 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 300 AND status = 'R')   
```  
  
## <a name="how-multiple-and-and-or-clauses-are-represented-in-the-criteria-pane"></a><span data-ttu-id="d8330-136">Как несколько предложений AND и OR представляются на панели критериев</span><span class="sxs-lookup"><span data-stu-id="d8330-136">How Multiple AND and OR Clauses Are Represented in the Criteria Pane</span></span>  
 <span data-ttu-id="d8330-137">Конструктор запросов и представлений выводит условия поиска на [панель критериев](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d8330-137">The Query and View Designer represents your search conditions in the [Criteria Pane](visual-database-tools.md).</span></span> <span data-ttu-id="d8330-138">Однако в некоторых случаях при использовании нескольких предложений, соединенных AND и OR, представление на панели критериев может отличаться от ожидаемого.</span><span class="sxs-lookup"><span data-stu-id="d8330-138">However, in some cases that involve multiple clauses linked with AND and OR, the representation in the Criteria Pane might not be what you expect.</span></span> <span data-ttu-id="d8330-139">Кроме того, при редактировании запроса на панели критериев или [панели диаграммы](diagram-pane-visual-database-tools.md)можно обнаружить, что инструкция SQL изменилась по сравнению с ранее заданной.</span><span class="sxs-lookup"><span data-stu-id="d8330-139">In addition, if you modify your query in the Criteria Pane or [Diagram Pane](diagram-pane-visual-database-tools.md), you might find that your SQL statement has been changed from what you entered.</span></span>  
  
 <span data-ttu-id="d8330-140">Эти правила определяют то, как предложения AND и OR отображаются на панели критериев:</span><span class="sxs-lookup"><span data-stu-id="d8330-140">In general, these rules dictate how AND and OR clauses appear in the Criteria Pane:</span></span>  
  
-   <span data-ttu-id="d8330-141">Все условия, соединенные AND, выводятся в столбце сетки **Фильтр** или в одном столбце **Или...** .</span><span class="sxs-lookup"><span data-stu-id="d8330-141">All conditions linked with AND appear in the **Filter** grid column or in the same **Or...** column.</span></span>  
  
-   <span data-ttu-id="d8330-142">Все условия, соединенные OR, выводятся в отдельных столбцах **Или...** .</span><span class="sxs-lookup"><span data-stu-id="d8330-142">All conditions linked with OR appear in separate **Or...** columns.</span></span>  
  
-   <span data-ttu-id="d8330-143">Если логический результат объединения предложений AND и OR заключается в том, что AND распространяется на несколько предложений OR, панель критериев представляет это в явной форме, повторяя предложение AND столько раз, сколько требуется.</span><span class="sxs-lookup"><span data-stu-id="d8330-143">If the logical result of a combination of AND and OR clauses is that the AND is distributed into several OR clauses, the Criteria Pane represents this explicitly by repeating the AND clause as many times as necessary.</span></span>  
  
 <span data-ttu-id="d8330-144">Например, на панели SQL можно создать нижеприведенное условие поиска, в котором два предложения, соединенные AND, имеют приоритет над третьим, соединенным OR:</span><span class="sxs-lookup"><span data-stu-id="d8330-144">For example, in the SQL pane you might create a search condition such as the following, in which two clauses linked with AND take precedence over a third one linked with OR:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  (job_lvl = 100) OR   
  (status = 'R')  
```  
  
 <span data-ttu-id="d8330-145">Конструктор запросов и представлений отображает данное предложение WHERE на панели критериев следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d8330-145">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="d8330-146">![Очередность предложений OR в области условий](../../database-engine/media//vs-criteriapane1.gif "Очередность предложений OR в области условий")</span><span class="sxs-lookup"><span data-stu-id="d8330-146">![OR clause precedence in the Criteria Pane](../../database-engine/media//vs-criteriapane1.gif "OR clause precedence in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="d8330-147">Однако если связанные предложения OR имеют приоритет над предложением AND, последнее повторяется для каждого предложения OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-147">However, if the linked OR clauses take precedence over an AND clause, the AND clause is repeated for each OR clause.</span></span> <span data-ttu-id="d8330-148">В результате предложение AND распространяется на каждое предложение OR.</span><span class="sxs-lookup"><span data-stu-id="d8330-148">This causes the AND clause to be distributed to each OR clause.</span></span> <span data-ttu-id="d8330-149">Например, на панели SQL было создано предложение WHERE, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="d8330-149">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ( (job_lvl = 100) OR   
  (status = 'R') )  
```  
  
 <span data-ttu-id="d8330-150">Конструктор запросов и представлений отображает данное предложение WHERE на панели критериев следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d8330-150">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="d8330-151">![Несколько предложений AND и OR в области условий](../../database-engine/media//vs-criteriapane2.gif "Несколько предложений AND и OR в области условий")</span><span class="sxs-lookup"><span data-stu-id="d8330-151">![Multiple AND and OR clauses in the Criteria Pane](../../database-engine/media//vs-criteriapane2.gif "Multiple AND and OR clauses in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="d8330-152">Если соединенные предложения OR включают только один столбец данных, конструктор запросов и представлений может поместить все предложение OR в одну ячейку сетки, устраняя необходимость повторения предложения AND.</span><span class="sxs-lookup"><span data-stu-id="d8330-152">If the linked OR clauses involve only one data column, the Query and View Designer can place the entire OR clause into a single cell of the grid, avoiding the need to repeat the AND clause.</span></span> <span data-ttu-id="d8330-153">Например, на панели SQL было создано предложение WHERE, подобное следующему:</span><span class="sxs-lookup"><span data-stu-id="d8330-153">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ((status = 'R') OR (status = 'A'))  
```  
  
 <span data-ttu-id="d8330-154">Конструктор запросов и представлений отображает данное предложение WHERE на панели критериев следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d8330-154">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="d8330-155">![Связанные предложения OR, определенные в области условий](../../database-engine/media//vs-criteriapane3.gif "Связанные предложения OR, определенные в области условий")</span><span class="sxs-lookup"><span data-stu-id="d8330-155">![Linked OR clauses defined in the Criteria Pane](../../database-engine/media//vs-criteriapane3.gif "Linked OR clauses defined in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="d8330-156">При внесении изменений в запрос (например при редактировании одного из значений на панели критериев), конструктор запросов и представлений повторно создает инструкцию SQL на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="d8330-156">If you make a change to the query (such as changing one of the values in the Criteria Pane), the Query and View Designer recreates the SQL statement in the SQL pane.</span></span> <span data-ttu-id="d8330-157">Воссозданная инструкция SQL аналогична представлению панели критериев, а не исходной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d8330-157">The recreated SQL statement will resemble the Criteria Pane display rather than your original statement.</span></span> <span data-ttu-id="d8330-158">Например, если панель критериев содержит распределенные предложения AND, результирующая инструкция на панели SQL создается повторно с явно распределенными предложениями AND.</span><span class="sxs-lookup"><span data-stu-id="d8330-158">For example, if the Criteria Pane contains distributed AND clauses, the resulting statement in the SQL pane will be recreated with explicit distributed AND clauses.</span></span> <span data-ttu-id="d8330-159">Дополнительные сведения см. в разделе «Работа AND с несколькими предложениями OR» ранее в этом подразделе.</span><span class="sxs-lookup"><span data-stu-id="d8330-159">For details, see "How AND Works with Multiple OR Clauses" earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8330-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8330-160">See Also</span></span>  
 [<span data-ttu-id="d8330-161">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d8330-161">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
