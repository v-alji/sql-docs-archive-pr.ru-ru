---
title: Включение или исключение строк (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- search criteria [SQL Server], WHERE clause
- included rows
- search conditions [SQL Server], HAVING clause
- search criteria [SQL Server], including rows
- row excluded in search [SQL Server]
- search criteria [SQL Server], HAVING clause
- search conditions [SQL Server], WHERE clause
- row included in search [SQL Server]
- excluding rows
ms.assetid: ba4e1202-31a2-444d-8365-c68a530ef223
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7b2d31c51296fa73a503e59a14adb60d79a61178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665184"
---
# <a name="include-or-exclude-rows-visual-database-tools"></a><span data-ttu-id="7301a-102">Включение или исключение строк (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7301a-102">Include or Exclude Rows (Visual Database Tools)</span></span>
  <span data-ttu-id="7301a-103">Чтобы ограничить число строк, возвращаемых запросом SELECT, создают условия поиска или критерии фильтрации.</span><span class="sxs-lookup"><span data-stu-id="7301a-103">To restrict the number of rows a SELECT query should return, you create search conditions or filter criteria.</span></span> <span data-ttu-id="7301a-104">В языке SQL условия поиска появляются в предложении инструкций WHERE или, если запрос статистический, в предложении HAVING.</span><span class="sxs-lookup"><span data-stu-id="7301a-104">In SQL, search conditions appear in the WHERE clause of the statement, or if you are creating an aggregate query, in the HAVING clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7301a-105">Можно также использовать условия поиска, чтобы задать, какие строки будут изменены запросами обновления, вставки результатов и значений, удаления или создания таблиц.</span><span class="sxs-lookup"><span data-stu-id="7301a-105">You can also use search conditions to indicate which rows are affected by an Update, Insert Results, Insert Values, Delete, or Make Table query.</span></span>  
  
 <span data-ttu-id="7301a-106">При выполнении запроса компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] проверяет и применяет условия поиска к каждой строке таблиц, где осуществляется поиск.</span><span class="sxs-lookup"><span data-stu-id="7301a-106">When the query runs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] examines and applies the search condition to each row in the tables you are searching.</span></span> <span data-ttu-id="7301a-107">Если строка соответствует условиям, она включается в запрос.</span><span class="sxs-lookup"><span data-stu-id="7301a-107">If the row meets the condition, it is included in the query.</span></span> <span data-ttu-id="7301a-108">Например, условие поиска всех сотрудников в определенном регионе может быть таким:</span><span class="sxs-lookup"><span data-stu-id="7301a-108">For example, a search condition that would find all the employees in a particular region might be:</span></span>  
  
```  
region = 'UK'  
```  
  
 <span data-ttu-id="7301a-109">Чтобы задать критерий включения строки в результат, можно применять несколько условий поиска.</span><span class="sxs-lookup"><span data-stu-id="7301a-109">To establish the criteria for including a row in a result, you can use multiple search conditions.</span></span> <span data-ttu-id="7301a-110">Например, следующий критерий состоит из двух условий поиска.</span><span class="sxs-lookup"><span data-stu-id="7301a-110">For example, the following search criterion consists of two search conditions.</span></span> <span data-ttu-id="7301a-111">Запрос включает строку в результирующий набор только в том случае, если она удовлетворяет обоим условиям.</span><span class="sxs-lookup"><span data-stu-id="7301a-111">The query includes a row in the result set only if that row satisfies both of the conditions.</span></span>  
  
```  
region = 'UK' AND product_line = 'Housewares'  
```  
  
 <span data-ttu-id="7301a-112">Эти условия можно комбинировать с помощью ключевых слов AND и OR.</span><span class="sxs-lookup"><span data-stu-id="7301a-112">You can combine these conditions with AND or OR.</span></span> <span data-ttu-id="7301a-113">В предыдущем примере использовался AND.</span><span class="sxs-lookup"><span data-stu-id="7301a-113">The previous example uses AND.</span></span> <span data-ttu-id="7301a-114">В следующем критерии, напротив, используется OR.</span><span class="sxs-lookup"><span data-stu-id="7301a-114">In contrast, the following criterion uses OR.</span></span> <span data-ttu-id="7301a-115">Результирующий набор будет включать в себя все строки, удовлетворяющие любому из условий поиска или обоим:</span><span class="sxs-lookup"><span data-stu-id="7301a-115">The result set will include any row that satisfies either or both of the search conditions:</span></span>  
  
```  
region = 'UK' OR product_line = 'Housewares'  
```  
  
 <span data-ttu-id="7301a-116">Можно даже комбинировать условия поиска по одному столбцу.</span><span class="sxs-lookup"><span data-stu-id="7301a-116">You can even combine search conditions on a single column.</span></span> <span data-ttu-id="7301a-117">Например, следующий критерий сочетает два условия поиска по столбцу region:</span><span class="sxs-lookup"><span data-stu-id="7301a-117">For example, the following criterion combines two conditions on the region column:</span></span>  
  
```  
region = 'UK' OR region = 'US'  
```  
  
 <span data-ttu-id="7301a-118">Дополнительные сведения о сочетании условий поиска см. в следующих подразделах:</span><span class="sxs-lookup"><span data-stu-id="7301a-118">For details about combining search conditions, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7301a-119">Обозначения для условий комбинированного поиска на панели критериев (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7301a-119">Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;</span></span>](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
  
-   [<span data-ttu-id="7301a-120">Указание нескольких условий поиска для одного столбца (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7301a-120">Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
-   [<span data-ttu-id="7301a-121">Указание нескольких условий поиска для нескольких столбцов (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7301a-121">Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;</span></span>](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md)  
  
-   [<span data-ttu-id="7301a-122">Объединение условий, если приоритет имеет оператор AND (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7301a-122">Combine Conditions When AND Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-and-has-precedence-visual-database-tools.md)  
  
-   [<span data-ttu-id="7301a-123">Соединение условий, если приоритет имеет оператор OR (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7301a-123">Combine Conditions When OR Has Precedence &#40;Visual Database Tools&#41;</span></span>](combine-conditions-when-or-has-precedence-visual-database-tools.md)  
  
## <a name="examples"></a><span data-ttu-id="7301a-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="7301a-124">Examples</span></span>  
 <span data-ttu-id="7301a-125">Несколько примеров запросов с использованием различных операторов и критериев фильтрации строк.</span><span class="sxs-lookup"><span data-stu-id="7301a-125">Here are some examples of queries using various operators and row criteria:</span></span>  
  
-   <span data-ttu-id="7301a-126">**Литерал** . Текстовое, численное, логическое значение или значение даты.</span><span class="sxs-lookup"><span data-stu-id="7301a-126">**Literal** A single text, numeric, date, or logical value.</span></span> <span data-ttu-id="7301a-127">В следующем примере литерал используется для поиска всех сотрудников, работающих в Великобритании:</span><span class="sxs-lookup"><span data-stu-id="7301a-127">The following example uses a literal to find all rows for employees in the United Kingdom:</span></span>  
  
    ```  
    WHERE region = 'UK'  
    ```  
  
-   <span data-ttu-id="7301a-128">**Ссылка на столбец** . Сравнение значений одного столбца со значениями в другом.</span><span class="sxs-lookup"><span data-stu-id="7301a-128">**Column reference** Compares the values in one column with the values in another.</span></span> <span data-ttu-id="7301a-129">В следующем примере в таблице `products` ищутся все строки, где стоимость производства ниже стоимости доставки:</span><span class="sxs-lookup"><span data-stu-id="7301a-129">The following example searches a `products` table for all rows in which the value of the production cost is lower than the shipping cost:</span></span>  
  
    ```  
    WHERE prod_cost < ship_cost  
    ```  
  
-   <span data-ttu-id="7301a-130">**Функция** . Ссылка на функцию, которую серверная часть базы данных может разрешить для вычисления значения, использующегося в поиске.</span><span class="sxs-lookup"><span data-stu-id="7301a-130">**Function** A reference to a function that the database back-end can resolve to calculate a value for the search.</span></span> <span data-ttu-id="7301a-131">Это может быть функция, определенная сервером базы данных, или определяемая пользователем функция, возвращающая скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="7301a-131">The function can be a function defined by the database server or a user-defined function that returns a scalar value.</span></span> <span data-ttu-id="7301a-132">В следующем примере ищутся все заказы, сделанные сегодня (функция GETDATE( ) возвращает текущую дату):</span><span class="sxs-lookup"><span data-stu-id="7301a-132">The following example searches for orders placed today (the GETDATE( ) function returns the current date):</span></span>  
  
    ```  
    WHERE order_date = GETDATE()  
    ```  
  
-   <span data-ttu-id="7301a-133">**NULL** . В следующем примере в таблице `authors` ищутся все авторы, имя которых сохранено в файле:</span><span class="sxs-lookup"><span data-stu-id="7301a-133">**NULL** The following example searches an `authors` table for all authors who have a first name on file:</span></span>  
  
    ```  
    WHERE au_fname IS NOT NULL  
    ```  
  
-   <span data-ttu-id="7301a-134">**Вычисление** . Результат вычисления, в котором могут участвовать литералы, ссылки на столбцы и другие выражения.</span><span class="sxs-lookup"><span data-stu-id="7301a-134">**Calculation** The result of a calculation that can involve literals, column references, or other expressions.</span></span> <span data-ttu-id="7301a-135">В следующем примере в таблице `products` ищутся все строки, где розничная цена в два раза превышает стоимость производства:</span><span class="sxs-lookup"><span data-stu-id="7301a-135">The following example searches a `products` table to find all rows in which the retail sales price is more than twice the production cost:</span></span>  
  
    ```  
    WHERE sales_price > (prod_cost * 2)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7301a-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="7301a-136">See Also</span></span>  
 <span data-ttu-id="7301a-137">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7301a-137">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="7301a-138">[Укажите условия поиска &#40;визуальные инструменты для баз данных&#41;](specify-search-criteria-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7301a-138">[Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7301a-139">Запрос с параметрами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="7301a-139">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](query-with-parameters-visual-database-tools.md)  
  
  
