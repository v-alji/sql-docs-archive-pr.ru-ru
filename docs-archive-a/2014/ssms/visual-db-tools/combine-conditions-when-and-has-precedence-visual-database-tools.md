---
title: Объединение условий, если приоритет имеет оператор AND (визуальные инструменты для баз данных) | Документация Майкрософт
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
- combining search conditions
- AND, Criteria pane
ms.assetid: 450eb2eb-6ea3-405b-8dd2-1ff926c016e7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 917d5381bc83083ee1fa3c07375945c0908da521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727809"
---
# <a name="combine-conditions-when-and-has-precedence-visual-database-tools"></a><span data-ttu-id="25586-102">Объединение условий, если приоритет имеет оператор AND (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="25586-102">Combine Conditions When AND Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="25586-103">Для объединения условий с оператором AND столбец добавляется к запросу дважды для каждого из условий.</span><span class="sxs-lookup"><span data-stu-id="25586-103">To combine conditions with AND, you add the column to the query twice--once for each condition.</span></span> <span data-ttu-id="25586-104">Для объединения условий с оператором OR первое условие необходимо вставить в столбец "Фильтр", а дополнительные условия — в столбец **Или...**</span><span class="sxs-lookup"><span data-stu-id="25586-104">To combine conditions with OR, you put the first one in the Filter column and additional conditions into an **Or...** column.</span></span>  
  
 <span data-ttu-id="25586-105">Предположим, что нужно найти или служащих, проработавших в компании более пяти лет на низкооплачиваемых должностях, или служащих на должностях среднего уровня, независимо от их стажа работы.</span><span class="sxs-lookup"><span data-stu-id="25586-105">For example, imagine that you want to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs regardless of their hire date.</span></span> <span data-ttu-id="25586-106">Этому запросу требуется три условия, два из которых связаны с оператором AND:</span><span class="sxs-lookup"><span data-stu-id="25586-106">This query requires three conditions, two of them linked with AND:</span></span>  
  
-   <span data-ttu-id="25586-107">Служащие со стажем более пяти лет и (AND) уровнем должности 100.</span><span class="sxs-lookup"><span data-stu-id="25586-107">Employees with a hire date earlier than five years ago AND with a job level of 100.</span></span>  
  
     <span data-ttu-id="25586-108">-или-</span><span class="sxs-lookup"><span data-stu-id="25586-108">-or-</span></span>  
  
-   <span data-ttu-id="25586-109">Служащие с уровнем должности 200.</span><span class="sxs-lookup"><span data-stu-id="25586-109">Employees with a job level of 200.</span></span>  
  
### <a name="to-combine-conditions-when-and-has-precedence"></a><span data-ttu-id="25586-110">Сочетание условий, если оператор AND имеет больший приоритет</span><span class="sxs-lookup"><span data-stu-id="25586-110">To combine conditions when AND has precedence</span></span>  
  
1.  <span data-ttu-id="25586-111">На [панель критериев](visual-database-tools.md)добавьте столбцы данных для поиска.</span><span class="sxs-lookup"><span data-stu-id="25586-111">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="25586-112">Если необходимо выполнить поиск в одном столбце по двум и более условиям, связанным оператором AND, в сетку необходимо добавить имя столбца данных столько раз, сколько имеется искомых значений.</span><span class="sxs-lookup"><span data-stu-id="25586-112">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="25586-113">В столбце **Фильтр** введите все условия, которые нужно связать оператором AND.</span><span class="sxs-lookup"><span data-stu-id="25586-113">In the **Filter** column, enter all the conditions that you want to link with AND.</span></span> <span data-ttu-id="25586-114">Например, чтобы связать условия поиска в столбцах `hire_date` и `job_lvl` оператором AND, введите в столбец «Фильтр» значения `< '1/1/91'` и `= 100`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="25586-114">For example, to link conditions with AND that search the `hire_date` and `job_lvl` columns, enter the values `< '1/1/91'` and `= 100`, respectively, in the Filter column.</span></span>  
  
     <span data-ttu-id="25586-115">На основании этих строк сетки в инструкции на [панели SQL](sql-pane-visual-database-tools.md)будет сформировано следующее предложение WHERE:</span><span class="sxs-lookup"><span data-stu-id="25586-115">These grid entries produce the following WHERE clause in the statement in the [SQL Pane](sql-pane-visual-database-tools.md):</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91') AND  
      (job_lvl = 100)  
    ```  
  
3.  <span data-ttu-id="25586-116">В столбце сетки **Или...** введите условия, которые нужно связать оператором OR.</span><span class="sxs-lookup"><span data-stu-id="25586-116">In the **Or...** grid column, enter conditions that you want to link with OR.</span></span> <span data-ttu-id="25586-117">Например, чтобы добавить условие, выполняющее поиск другого значения в столбце `job_lvl` , введите дополнительное значение в столбец **Или...** , например `= 200`.</span><span class="sxs-lookup"><span data-stu-id="25586-117">For example, to add a condition that searches for another value in the `job_lvl` column, enter an additional value in the **Or...** column, such as `= 200`.</span></span>  
  
     <span data-ttu-id="25586-118">Ввод еще одного значения в столбце **Или...** добавляет к предложению WHERE в инструкции на панели "SQL" еще одно условие:</span><span class="sxs-lookup"><span data-stu-id="25586-118">Adding a value in the **Or...** column adds another condition to the WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (hire_date < '01/01/91' ) AND  
      (job_lvl = 100) OR   
      (job_lvl = 200)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="25586-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="25586-119">See Also</span></span>  
 <span data-ttu-id="25586-120">[Объединение условий, когда или имеет приоритет &#40;визуальных инструментов для баз данных&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="25586-120">[Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;](combine-conditions-when-or-has-precedence-visual-database-tools.md) </span></span>  
 <span data-ttu-id="25586-121">[Соглашения для комбинирования условий поиска на панели критериев &#40;визуальных инструментов для баз данных&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="25586-121">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 <span data-ttu-id="25586-122">[Правила ввода значений поиска &#40;визуальных инструментов для баз данных&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="25586-122">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="25586-123">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="25586-123">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
