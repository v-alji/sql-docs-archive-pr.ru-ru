---
title: Создание самосоединения вручную (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- self-joins
- manual joins [SQL Server]
- joins [SQL Server], self
ms.assetid: 910ed516-cb84-481b-95d0-cba3e89afdba
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31e125fdfe0f7f285ea679cfe85356d1aa10353a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665213"
---
# <a name="create-self-joins-manually-visual-database-tools"></a><span data-ttu-id="1246e-102">Создание самосоединения вручную (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="1246e-102">Create Self-Joins Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="1246e-103">Самосоединение таблицы может быть создано даже в случае отсутствия рефлексивной связи таблица — база данных.</span><span class="sxs-lookup"><span data-stu-id="1246e-103">You can join a table to itself even if the table does not have a reflexive relationship in the database.</span></span> <span data-ttu-id="1246e-104">Например, самосоединение может быть использовано для извлечения сведений о парах авторов, живущих в одном городе.</span><span class="sxs-lookup"><span data-stu-id="1246e-104">For example, you can use a self-join to find pairs of authors living in the same city.</span></span>  
  
 <span data-ttu-id="1246e-105">Как и для любого другого соединения, для самосоединения требуется не менее двух таблиц.</span><span class="sxs-lookup"><span data-stu-id="1246e-105">As with any join, a self-join requires at least two tables.</span></span> <span data-ttu-id="1246e-106">Различие состоит в том, что при самосоединении в роли второй таблицы выступает копия первой таблицы.</span><span class="sxs-lookup"><span data-stu-id="1246e-106">The difference is that, instead of adding a second table to the query, you add a second instance of the same table.</span></span> <span data-ttu-id="1246e-107">Таким образом можно сравнивать столбцы двух экземпляров одной таблицы, что позволяет сравнивать значения элементов одного столбца друг с другом.</span><span class="sxs-lookup"><span data-stu-id="1246e-107">That way, you can compare a column in the first instance of the table to the same column in the second instance, which allows you to compare the values in a column to each other.</span></span> <span data-ttu-id="1246e-108">[Конструктор запросов и представлений](visual-database-tools.md) присваивает второму экземпляру таблицы псевдоним.</span><span class="sxs-lookup"><span data-stu-id="1246e-108">The [Query and View Designer](visual-database-tools.md) assigns an alias to the second instance of the table.</span></span>  
  
 <span data-ttu-id="1246e-109">Например, если создается самосоединение для получения всех пар авторов, живущих в г. Беркли, необходимо сравнить столбец `city` первого экземпляра таблицы со столбцом `city` второго экземпляра таблицы.</span><span class="sxs-lookup"><span data-stu-id="1246e-109">For example, if you are creating a self-join to find all pairs of authors within Berkeley, you compare the `city` column in the first instance of the table against the `city` column in the second instance.</span></span> <span data-ttu-id="1246e-110">Результирующий запрос может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="1246e-110">The resulting query might look like the following:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="1246e-111">Для создания самосоединения часто требуется вводить несколько условий соединения.</span><span class="sxs-lookup"><span data-stu-id="1246e-111">Creating a self-join often requires multiple join conditions.</span></span> <span data-ttu-id="1246e-112">Упомянутая особенность поясняется в представленном ниже примере:</span><span class="sxs-lookup"><span data-stu-id="1246e-112">To understand why, consider the result of the preceding query:</span></span>  
  
```  
Cheryl Carson       Cheryl Carson  
Abraham Bennet      Abraham Bennet  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="1246e-113">Первая строка бесполезна, поскольку в ней указано, что Cheryl Carson живет в том же городе, что и Cheryl Carson.</span><span class="sxs-lookup"><span data-stu-id="1246e-113">The first row is useless; it indicates that Cheryl Carson lives in the same city as Cheryl Carson.</span></span> <span data-ttu-id="1246e-114">Во второй строке также содержатся бесполезные данные.</span><span class="sxs-lookup"><span data-stu-id="1246e-114">The second row is equally useless.</span></span> <span data-ttu-id="1246e-115">Чтобы исключить указанные бесполезные данные, необходимо добавить условие, обеспечивающее вывод только тех строк, которые содержат данные о разных авторах.</span><span class="sxs-lookup"><span data-stu-id="1246e-115">To eliminate this useless data, you add another condition retaining only those result rows in which the two author names describe different authors.</span></span> <span data-ttu-id="1246e-116">Результирующий запрос может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="1246e-116">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             <> authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="1246e-117">Результирующий набор улучшен:</span><span class="sxs-lookup"><span data-stu-id="1246e-117">The result set is improved:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="1246e-118">Однако две результирующие строки содержат избыточные данные.</span><span class="sxs-lookup"><span data-stu-id="1246e-118">But the two result rows are redundant.</span></span> <span data-ttu-id="1246e-119">В первой строке указано, что автор с именем Carson проживает в одном городе с Bennet, а вторая строка говорит о том, что автор с именем «Bennet» проживает в одном городе с Carson.</span><span class="sxs-lookup"><span data-stu-id="1246e-119">The first says Carson lives in the same city as Bennet, and the second says the Bennet lives in the same city as Carson.</span></span> <span data-ttu-id="1246e-120">Подобного дублирования данных можно избежать, если во втором условии соединения заменить оператор «не равно» на «меньше».</span><span class="sxs-lookup"><span data-stu-id="1246e-120">To eliminate this redundancy, you can alter the second join condition from "not equals" to "less than."</span></span> <span data-ttu-id="1246e-121">Результирующий запрос может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="1246e-121">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             < authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="1246e-122">Результирующий набор имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="1246e-122">And the result set looks like this:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
```  
  
### <a name="to-create-a-self-join-manually"></a><span data-ttu-id="1246e-123">Создание самосоединения вручную</span><span class="sxs-lookup"><span data-stu-id="1246e-123">To create a self-join manually</span></span>  
  
1.  <span data-ttu-id="1246e-124">На [панель диаграммы](diagram-pane-visual-database-tools.md) добавьте необходимую таблицу или возвращающий табличное значение объект.</span><span class="sxs-lookup"><span data-stu-id="1246e-124">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the table or table-valued object you want to work with.</span></span>  
  
2.  <span data-ttu-id="1246e-125">Затем еще раз добавьте эту таблицу, чтобы на панели диаграмм отображалось два экземпляра одной таблицы или возвращающего табличное значение объекта.</span><span class="sxs-lookup"><span data-stu-id="1246e-125">Add the same table again, so that the Diagram pane shows the same table or table-valued object twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="1246e-126">Конструктор запросов и представлений присваивает второму экземпляру псевдоним, добавляя порядковый номер к имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="1246e-126">The Query and View Designer assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="1246e-127">Кроме того, конструктор запросов и представлений создает внутри панели диаграмм соединение указанных экземпляров таблицы или возвращающего табличное значение объекта.</span><span class="sxs-lookup"><span data-stu-id="1246e-127">In addition, the Query and View Designer creates a join line between the two occurrences of the table or table-valued object within the Diagram pane.</span></span>  
  
3.  <span data-ttu-id="1246e-128">Щелкните правой кнопкой мыши указанное соединение и в контекстном меню выберите **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="1246e-128">Right-click the join line and choose **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="1246e-129">В окне свойств выберите вкладку **Условие и тип соединения** и нажмите кнопку с многоточием **(...)** справа от нужного свойства.</span><span class="sxs-lookup"><span data-stu-id="1246e-129">In the Properties window click **Join Condition and Type** and click the **ellipses (...)** to the right of the property.</span></span>  
  
5.  <span data-ttu-id="1246e-130">В [диалоговом окне "Соединение"](join-dialog-box-visual-database-tools.md) измените оператор сравнения первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="1246e-130">In the [Join Dialog Box](join-dialog-box-visual-database-tools.md) change the comparison operator between the primary keys as required.</span></span> <span data-ttu-id="1246e-131">Например, можно выбрать оператор «меньше» (<).</span><span class="sxs-lookup"><span data-stu-id="1246e-131">For example, you might change the operator to less than (<).</span></span>  
  
6.  <span data-ttu-id="1246e-132">Создайте дополнительное условие соединения, например authors.zip = authors1.zip, перетащив имя основного столбца соединения в первом экземпляре таблицы или возвращающего табличное значение объекта в область соответствующего столбца второго экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1246e-132">Create the additional join condition (for example, authors.zip = authors1.zip) by dragging the name of the primary join column in the first occurrence of the table or table-valued object and dropping it on the corresponding column in the second occurrence.</span></span>  
  
7.  <span data-ttu-id="1246e-133">Задайте другие параметры запроса, например выходные столбцы, условия поиска и порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="1246e-133">Specify other options for the query such as output columns, search conditions, and sort order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1246e-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="1246e-134">See Also</span></span>  
 <span data-ttu-id="1246e-135">[Автоматическое создание самосоединений &#40;визуальных инструментов для баз данных&#41;](create-self-joins-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1246e-135">[Create Self-Joins Automatically &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1246e-136">Запросы с соединениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="1246e-136">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
