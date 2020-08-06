---
title: Создание внешних соединений (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- joins [SQL Server], outer
ms.assetid: 18de47b1-f936-427d-b852-fe6d20334f71
author: stevestein
ms.author: sstein
ms.openlocfilehash: f02c0be049e2e75e1a657bb3c027d20430d562cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750427"
---
# <a name="create-outer-joins-visual-database-tools"></a><span data-ttu-id="e77dd-102">Создание внешних соединений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e77dd-102">Create Outer Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="e77dd-103">По умолчанию [Конструктор запросов и представлений](visual-database-tools.md) создает внутреннее соединение таблиц.</span><span class="sxs-lookup"><span data-stu-id="e77dd-103">By default, the [Query and View Designer](visual-database-tools.md) creates an inner join between tables.</span></span> <span data-ttu-id="e77dd-104">Внутренние соединения исключают строки, не соответствующие строке из другой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e77dd-104">Inner joins eliminate the rows that do not match with a row from the other table.</span></span> <span data-ttu-id="e77dd-105">Однако внешние соединения возвращают все строки хотя бы из одной таблицы или представления, упомянутых в предложении FROM, если эти строки удовлетворяют условиям поиска WHERE или HAVING.</span><span class="sxs-lookup"><span data-stu-id="e77dd-105">Outer joins, however, return all rows from at least one of the tables or views mentioned in the FROM clause, as long as those rows meet any WHERE or HAVING search conditions.</span></span> <span data-ttu-id="e77dd-106">Если необходимо включить строки данных, которые не имеют совпадений в соединяемой таблице, в результирующий набор, можно создать внешнее соединение.</span><span class="sxs-lookup"><span data-stu-id="e77dd-106">If you want to include data rows in the result set that do not have a match in the joined table, you can create an outer join.</span></span>  
  
 <span data-ttu-id="e77dd-107">При создании внешнего соединения имеет значение порядок, в котором указывают таблицы в инструкции SQL (как показано на панели SQL).</span><span class="sxs-lookup"><span data-stu-id="e77dd-107">When you create an outer join, the order in which tables appear in the SQL statement (as reflected in the SQL pane) is significant.</span></span> <span data-ttu-id="e77dd-108">Первая таблица становится «левой» таблицей, а вторая — «правой»</span><span class="sxs-lookup"><span data-stu-id="e77dd-108">The first table you add becomes the "left" table and the second table becomes the "right" table.</span></span> <span data-ttu-id="e77dd-109">(Реальный порядок, в котором указываются таблицы на [панели диаграммы](diagram-pane-visual-database-tools.md) , несущественен.) При указании левого или правого внешнего соединения указывается порядок, в котором таблицы были добавлены в запрос, и порядок, в котором они появляются в инструкции SQL на [панели SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e77dd-109">(The actual order in which the tables appear in the [Diagram pane](diagram-pane-visual-database-tools.md) is not significant.) When you specify a left or right outer join, you are referring to the order in which the tables were added to the query and to the order in which they appear in the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-an-outer-join"></a><span data-ttu-id="e77dd-110">Создание внешнего соединения</span><span class="sxs-lookup"><span data-stu-id="e77dd-110">To create an outer join</span></span>  
  
1.  <span data-ttu-id="e77dd-111">Создайте соединение автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="e77dd-111">Create the join, either automatically or manually.</span></span> <span data-ttu-id="e77dd-112">Дополнительные сведения см. в статье [Автоматическое соединение таблиц (визуальные инструменты для баз данных)](join-tables-automatically-visual-database-tools.md) или [Соединение таблиц вручную (визуальные инструменты для баз данных)](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e77dd-112">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) or [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="e77dd-113">Выберите линию соединения на панели диаграммы, а затем в меню **Конструктор запросов** выберите **Выбрать все строки из \<tablename>** , указав команду, включающую таблицу, дополнительные строки которой необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="e77dd-113">Select the join line in the Diagram pane, and then from the **Query Designer** menu, choose **Select All Rows from \<tablename>**, selecting the command that includes the table whose extra rows you want to include.</span></span>  
  
    -   <span data-ttu-id="e77dd-114">Выберите первую таблицу для создания левого внешнего соединения.</span><span class="sxs-lookup"><span data-stu-id="e77dd-114">Choose the first table to create a left outer join.</span></span>  
  
    -   <span data-ttu-id="e77dd-115">Выберите вторую таблицу для создания правого внешнего соединения.</span><span class="sxs-lookup"><span data-stu-id="e77dd-115">Choose the second table to create a right outer join.</span></span>  
  
    -   <span data-ttu-id="e77dd-116">Выберите обе таблицы для создания полного внешнего соединения.</span><span class="sxs-lookup"><span data-stu-id="e77dd-116">Choose both tables to create a full outer join.</span></span>  
  
 <span data-ttu-id="e77dd-117">При указании внешнего соединения конструктор запросов и представлений изменяет линию соединения для отображения внешнего соединения.</span><span class="sxs-lookup"><span data-stu-id="e77dd-117">When you specify an outer join, the Query and View Designer modifies the join line to indicate an outer join.</span></span>  
  
 <span data-ttu-id="e77dd-118">Кроме того, конструктор запросов и представлений изменяет инструкцию SQL на панели SQL для отражения изменений типа соединения, как показано в следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="e77dd-118">In addition, the Query and View Designer modifies the SQL statement in the SQL pane to reflect the change in join type, as shown in the following statement:</span></span>  
  
```  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
```  
  
 <span data-ttu-id="e77dd-119">Так как внешнее соединение включает несовпадающие строки, можно использовать его для поиска строк, которые нарушают ограничение внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="e77dd-119">Because an outer join includes unmatched rows, you can use it to find rows that violate foreign key constraints.</span></span> <span data-ttu-id="e77dd-120">Чтобы сделать это, надо создать внешнее соединение и добавить условие поиска строк, в которых значение первичного ключевого столбца самой правой таблицы равно NULL.</span><span class="sxs-lookup"><span data-stu-id="e77dd-120">To do so, you create an outer join and then add a search condition to find rows in which the primary key column of the rightmost table is null.</span></span> <span data-ttu-id="e77dd-121">Например, следующее внешнее соединение находит строки в таблице `employee` , которая не содержит соответствующих строк в таблице `jobs` :</span><span class="sxs-lookup"><span data-stu-id="e77dd-121">For example, the following outer join finds rows in the `employee` table that do not have corresponding rows in the `jobs` table:</span></span>  
  
```  
SELECT employee.emp_id, employee.job_id  
FROM employee LEFT OUTER JOIN jobs   
   ON employee.job_id = jobs.job_id  
WHERE (jobs.job_id IS NULL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="e77dd-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="e77dd-122">See Also</span></span>  
 <span data-ttu-id="e77dd-123">[Запрос с помощью соединений &#40;визуальных инструментов для баз данных&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e77dd-123">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e77dd-124">Диалоговое окно "Соединение" (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e77dd-124">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
