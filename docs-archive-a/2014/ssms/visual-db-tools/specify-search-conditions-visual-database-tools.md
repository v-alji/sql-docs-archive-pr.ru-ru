---
title: Указание условий поиска (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- choosing search criteria
- search conditions [SQL Server], specifying
- search criteria [SQL Server], specifying conditions
ms.assetid: 18e2c759-68ec-4efe-b208-2f73418cd9bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa5dab8326de079c385a3a508bc1b01b1ee1247d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659065"
---
# <a name="specify-search-conditions-visual-database-tools"></a><span data-ttu-id="661f2-102">Указание условий поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="661f2-102">Specify Search Conditions (Visual Database Tools)</span></span>
  <span data-ttu-id="661f2-103">Можно указать строки данных, которые появятся в результате запроса, задав условия поиска.</span><span class="sxs-lookup"><span data-stu-id="661f2-103">You can specify the data rows that appear in your query by specifying search conditions.</span></span> <span data-ttu-id="661f2-104">Например, при выполнении запроса к таблице `employee` можно указать, что хотите найти только работников, которые работают в определенной области.</span><span class="sxs-lookup"><span data-stu-id="661f2-104">For example, if you are querying an `employee` table, you can specify that you want to find only the employees who work in a particular region.</span></span>  
  
 <span data-ttu-id="661f2-105">Условия поиска указываются с помощью выражений.</span><span class="sxs-lookup"><span data-stu-id="661f2-105">You specify search conditions using an expression.</span></span> <span data-ttu-id="661f2-106">Наиболее часто используемое выражение состоит из оператора и искомого значения.</span><span class="sxs-lookup"><span data-stu-id="661f2-106">Most commonly the expression consists of an operator and a search value.</span></span> <span data-ttu-id="661f2-107">Например, чтобы найти работников в определенной области продаж, можно указать следующий критерий поиска для столбца `region` :</span><span class="sxs-lookup"><span data-stu-id="661f2-107">For example, to find employees in a particular sales region, you might specify the following search criterion for the `region` column:</span></span>  
  
```  
='UK'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="661f2-108">При работе с несколькими таблицами конструктор запросов и представлений проверяет каждое условие поиска, чтобы определить, будет ли соединение результатом сравнения.</span><span class="sxs-lookup"><span data-stu-id="661f2-108">If you are working with multiple tables, the Query and View Designer examines each search condition to determine whether the comparison you are making results in a join.</span></span> <span data-ttu-id="661f2-109">Если да, то конструктор запросов и представлений автоматически преобразует условие поиска в соединение.</span><span class="sxs-lookup"><span data-stu-id="661f2-109">If so, the Query and View Designer automatically converts the search condition into a join.</span></span> <span data-ttu-id="661f2-110">Дополнительные сведения см. в статье [Автоматическое соединение таблиц (визуальные инструменты для баз данных)](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="661f2-110">For more information, see [Join Tables Automatically &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-specify-search-conditions"></a><span data-ttu-id="661f2-111">Указание условий поиска</span><span class="sxs-lookup"><span data-stu-id="661f2-111">To specify search conditions</span></span>  
  
1.  <span data-ttu-id="661f2-112">Если это еще не сделано, нужно добавить на панели критериев столбцы или выражения, которые необходимо использовать в условиях поиска.</span><span class="sxs-lookup"><span data-stu-id="661f2-112">If you have not done so already, add the columns or expressions that you want to use within your search condition to the Criteria pane.</span></span>  
  
     <span data-ttu-id="661f2-113">Если при создании запроса SELECT нежелательно, чтобы столбцы поиска или выражения появлялись в выходных данных запроса, очистите столбец **Выход** для каждого столбца или выражения, чтобы убрать их из числа выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="661f2-113">If you are creating a Select query and do not want the search columns or expressions to appear in the query output, clear the **Output** column for each search column or expression to remove them as output columns.</span></span>  
  
2.  <span data-ttu-id="661f2-114">Найдите строку, содержащую столбец данных или выражение поиска, и в столбце **Фильтр** введите условие поиска.</span><span class="sxs-lookup"><span data-stu-id="661f2-114">Locate the row containing the data column or expression to search, and then in the **Filter** column, enter a search condition.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="661f2-115">Если не ввести ни одного оператора, конструктор запросов и представлений автоматически вставит оператор равенства «=».</span><span class="sxs-lookup"><span data-stu-id="661f2-115">If you do not enter an operator, the Query and View Designer automatically inserts the equality operator "=".</span></span>  
  
 <span data-ttu-id="661f2-116">Конструктор запросов и представлений обновляет инструкцию SQL на [панели SQL](sql-pane-visual-database-tools.md) , добавляя или изменяя предложение WHERE.</span><span class="sxs-lookup"><span data-stu-id="661f2-116">The Query and View Designer updates the SQL statement in the [SQL Pane](sql-pane-visual-database-tools.md) by adding or modifying the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661f2-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="661f2-117">See Also</span></span>  
 <span data-ttu-id="661f2-118">[Правила ввода значений поиска &#40;визуальных инструментов для баз данных&#41;](rules-for-entering-search-values-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="661f2-118">[Rules for Entering Search Values &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="661f2-119">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="661f2-119">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
