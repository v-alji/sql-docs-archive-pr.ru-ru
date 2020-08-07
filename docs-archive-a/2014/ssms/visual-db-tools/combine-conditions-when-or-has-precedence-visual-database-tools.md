---
title: Объединение условий, если приоритет имеет оператор OR (визуальные инструменты для баз данных) | Документация Майкрософт
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
- OR operator
ms.assetid: b30f5ac9-25e7-4163-80ed-44e4bccb455d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8be0d2f783c28662eb01f6bf191dc24d339534f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727802"
---
# <a name="combine-conditions-when-or-has-precedence-visual-database-tools"></a><span data-ttu-id="507c1-102">Соединение условий, если приоритет имеет оператор OR (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="507c1-102">Combine Conditions When OR Has Precedence (Visual Database Tools)</span></span>
  <span data-ttu-id="507c1-103">Чтобы связать условия, оператором OR и дать им приоритет над условиями, связанными оператором AND, необходимо повторить условие, связанное оператором AND, для каждого условия, связанного оператором OR.</span><span class="sxs-lookup"><span data-stu-id="507c1-103">To link conditions with OR and give them precedence over conditions linked with AND, you must repeat the AND condition for each OR condition.</span></span>  
  
 <span data-ttu-id="507c1-104">Например, предположим, что нужно найти всех служащих, которые проработали в компании более пяти лет и имеют самую низшую должность или вышли на пенсию.</span><span class="sxs-lookup"><span data-stu-id="507c1-104">For example, imagine that you want to find all employees who have been with the company more than five years and have lower-level jobs or are retired.</span></span> <span data-ttu-id="507c1-105">Этот запрос требует трех условий: одного условия, связанного с двумя дополнительными оператором AND:</span><span class="sxs-lookup"><span data-stu-id="507c1-105">This query requires three conditions, a single condition linked to two additional conditions with AND:</span></span>  
  
-   <span data-ttu-id="507c1-106">служащие, принятые на работу ранее, чем пять лет назад;</span><span class="sxs-lookup"><span data-stu-id="507c1-106">Employees with a hire date earlier than five years ago, and</span></span>  
  
-   <span data-ttu-id="507c1-107">служащие, у которых уровень должности равен 100 или состояние имеет значение равен «R» (для покинувших компанию).</span><span class="sxs-lookup"><span data-stu-id="507c1-107">Employees with a job level of 100 or whose status is "R" (for retired).</span></span>  
  
 <span data-ttu-id="507c1-108">В следующей процедуре показано, как создать такой тип запроса на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="507c1-108">The following procedure illustrates how to create this type of query in the Criteria pane.</span></span>  
  
### <a name="to-combine-conditions-when-or-has-precedence"></a><span data-ttu-id="507c1-109">Соединение условий, с приоритетом оператора OR</span><span class="sxs-lookup"><span data-stu-id="507c1-109">To combine conditions when OR has precedence</span></span>  
  
1.  <span data-ttu-id="507c1-110">На [панель критериев](visual-database-tools.md)добавьте столбцы данных для поиска.</span><span class="sxs-lookup"><span data-stu-id="507c1-110">In the [Criteria pane](visual-database-tools.md), add the data columns you want to search.</span></span> <span data-ttu-id="507c1-111">Если необходимо выполнить поиск в одном столбце по двум и более условиям, связанным оператором AND, в сетку необходимо добавить имя столбца данных столько раз, сколько имеется искомых значений.</span><span class="sxs-lookup"><span data-stu-id="507c1-111">If you want to search the same column using two or more conditions linked with AND, you must add the data column name to the grid once for each value you want to search.</span></span>  
  
2.  <span data-ttu-id="507c1-112">Создайте условия, которые должны быть связаны оператором OR, введя первое условие в столбец сетки **Фильтр** , а второе (и последующие условия) в отдельные столбцы **Или...**</span><span class="sxs-lookup"><span data-stu-id="507c1-112">Create the conditions to be linked with OR by entering the first one into the **Filter** grid column and the second (and subsequent ones) into separate **Or...** columns.</span></span> <span data-ttu-id="507c1-113">Например, чтобы создать условия, связанные оператором OR для поиска по столбцам `job_lvl` и `status` , введите `= 100` в столбец **Фильтр** для `job_lvl` и `= 'R'` в столбец **Или...** для `status`.</span><span class="sxs-lookup"><span data-stu-id="507c1-113">For example, to link conditions with OR that search the `job_lvl` and `status` columns, enter `= 100` in the **Filter** column for `job_lvl` and `= 'R'` in the **Or...** column for `status`.</span></span>  
  
     <span data-ttu-id="507c1-114">Ввод этих значении в сетку приводит к появлению такого предложения WHERE в инструкции на панели SQL:</span><span class="sxs-lookup"><span data-stu-id="507c1-114">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) OR (status = 'R')  
    ```  
  
3.  <span data-ttu-id="507c1-115">Создайте условие, связанное оператором AND, добавив его один раз для каждого условия, связанного оператором OR.</span><span class="sxs-lookup"><span data-stu-id="507c1-115">Create the AND condition by entering it once for each OR condition.</span></span> <span data-ttu-id="507c1-116">Поместите условие AND в тот же самый столбец сетки, в котором находится соответствующее условие OR.</span><span class="sxs-lookup"><span data-stu-id="507c1-116">Place each entry in the same grid column as the OR condition it corresponds to.</span></span> <span data-ttu-id="507c1-117">Например, чтобы добавить условие, связанное оператором AND для поиска по столбцу `hire_date` и применить его к обоим условиям, связанным оператором OR, введите `< '1/1/91'` в оба столбца: столбец критериев и столбец **Или...** .</span><span class="sxs-lookup"><span data-stu-id="507c1-117">For example, to add an AND condition that searches the `hire_date` column and applies to both OR conditions, enter `< '1/1/91'` in both the Criteria column and the **Or...** column.</span></span>  
  
     <span data-ttu-id="507c1-118">Ввод этих значении в сетку приводит к появлению такого предложения WHERE в инструкции на панели SQL:</span><span class="sxs-lookup"><span data-stu-id="507c1-118">Entering these values in the grid produces the following WHERE clause in the statement in the SQL pane:</span></span>  
  
    ```  
    WHERE (job_lvl = 100) AND   
      (hire_date < '01/01/91' ) OR  
      (status = 'R') AND   
      (hire_date < '01/01/91' )  
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="507c1-119">Можно повторить ввод предварительно введенного условия AND с помощью команд **Вырезать** и **Вставить** из меню **Правка** , чтобы продублировать его для других условий, связанных оператором OR.</span><span class="sxs-lookup"><span data-stu-id="507c1-119">You can repeat an AND condition by adding it once, and then using the **Cut** and **Paste** commands from the **Edit** menu to repeat it for other OR conditions.</span></span>  
  
 <span data-ttu-id="507c1-120">Предложение WHERE, созданное в конструкторе запросов и представлений, эквивалентно следующему предложению WHERE, в котором используются скобки для указания приоритета оператора OR над оператором AND:</span><span class="sxs-lookup"><span data-stu-id="507c1-120">The WHERE clause created by the Query and View Designer is equivalent to the following WHERE clause, which uses parentheses to specify the precedence of OR over AND:</span></span>  
  
```  
WHERE (job_lvl = 100 OR status = 'R') AND  
   (hire_date < '01/01/91')  
```  
  
> [!NOTE]  
>  <span data-ttu-id="507c1-121">Если ввести условия поиска в формате, представленном выше, в [панель SQL](sql-pane-visual-database-tools.md), но потом изменить запрос на панели диаграмм или панели критериев, то конструктор запросов и представлений заново создает инструкцию SQL, так чтобы она соответствовала форме с условием AND, явно распространенным на оба условия, связанные оператором OR.</span><span class="sxs-lookup"><span data-stu-id="507c1-121">If you enter the search conditions in the format shown immediately above in the [SQL Pane](sql-pane-visual-database-tools.md), but then make a change to the query in the Diagram or Criteria panes, the Query and View Designer recreates the SQL statement to match the form with the AND condition explicitly distributed to both OR conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507c1-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="507c1-122">See Also</span></span>  
 <span data-ttu-id="507c1-123">[Соглашения для комбинирования условий поиска на панели критериев &#40;визуальных инструментов для баз данных&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span><span class="sxs-lookup"><span data-stu-id="507c1-123">[Conventions for Combining Search Conditions in the Criteria Pane &#40;Visual Database Tools&#41;](conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md) </span></span>  
 [<span data-ttu-id="507c1-124">Определение критериев поиска (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="507c1-124">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
