---
title: Создание запросов на обновление (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], updating
- queries [SQL Server], types
- Update query
- updating tables
ms.assetid: 178b7b75-8078-4e61-b2a8-4719b9d8033d
author: stevestein
ms.author: sstein
ms.openlocfilehash: bbea575d544875dba73de923474cc11bbcb46a9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665208"
---
# <a name="create-update-queries-visual-database-tools"></a><span data-ttu-id="98c91-102">Создание запросов на обновление (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="98c91-102">Create Update Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="98c91-103">Запрос UPDATE позволяет изменить содержимое нескольких строк одной операцией.</span><span class="sxs-lookup"><span data-stu-id="98c91-103">You can change the contents of multiple rows in one operation by using an Update query.</span></span> <span data-ttu-id="98c91-104">Например, в таблице `titles` можно с помощью запроса UPDATE увеличить цену всех книг определенного издателя на 10%.</span><span class="sxs-lookup"><span data-stu-id="98c91-104">For example, in a `titles` table you can use an Update query to add 10% to the price of all books for a particular publisher.</span></span>  
  
 <span data-ttu-id="98c91-105">При создании запроса UPDATE нужно указать:</span><span class="sxs-lookup"><span data-stu-id="98c91-105">When you create an Update query, you specify:</span></span>  
  
-   <span data-ttu-id="98c91-106">обновляемую таблицу;</span><span class="sxs-lookup"><span data-stu-id="98c91-106">The table to update.</span></span>  
  
-   <span data-ttu-id="98c91-107">столбцы, содержимое которых необходимо обновить;</span><span class="sxs-lookup"><span data-stu-id="98c91-107">The columns whose contents you want to update.</span></span>  
  
-   <span data-ttu-id="98c91-108">значение или выражение, используемое для обновления отдельных столбцов;</span><span class="sxs-lookup"><span data-stu-id="98c91-108">The value or expression to use to update the individual columns.</span></span>  
  
-   <span data-ttu-id="98c91-109">условия поиска для выборки строк, которые требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="98c91-109">Search conditions to define the rows you want to update.</span></span>  
  
 <span data-ttu-id="98c91-110">Например, следующий запрос обновляет таблицу `titles` , добавляя 10% к цене всех изданий для одного издателя:</span><span class="sxs-lookup"><span data-stu-id="98c91-110">For example, the following query updates the `titles` table by adding 10% to the price of all titles for one publisher:</span></span>  
  
```  
UPDATE titles  
SET price = price * 1.1  
WHERE (pub_id = '0766')  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="98c91-111">Откат действия, произведенного запросом UPDATE, невозможен.</span><span class="sxs-lookup"><span data-stu-id="98c91-111">You cannot undo the action of executing an Update query.</span></span> <span data-ttu-id="98c91-112">В целях предосторожности создайте резервную копию данных перед выполнением запроса.</span><span class="sxs-lookup"><span data-stu-id="98c91-112">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-update-query"></a><span data-ttu-id="98c91-113">Создание запроса UPDATE</span><span class="sxs-lookup"><span data-stu-id="98c91-113">To create an Update query</span></span>  
  
1.  <span data-ttu-id="98c91-114">Добавьте таблицу, которую требуется обновить, на панель диаграмм.</span><span class="sxs-lookup"><span data-stu-id="98c91-114">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="98c91-115">В меню **Конструктор запросов** наведите указатель на пункт **Тип изменения**, а затем выберите пункт **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="98c91-115">From the **Query Designer** menu point to **Change Type**, and then click **Update**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="98c91-116">Если во время создания запроса на обновление на панели диаграммы отображается несколько таблиц, в конструкторе запросов и представлений появляется диалоговое окно [Выберите целевую таблицу для Insert Values](visual-database-tools.md) , в котором пользователь должен указать имя обновляемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="98c91-116">If more than one table is displayed in the Diagram pane when you start the Update query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="98c91-117">На панели диаграмм установите флажки рядом с каждым столбцом, для которого необходимо обновить значения.</span><span class="sxs-lookup"><span data-stu-id="98c91-117">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="98c91-118">Эти столбцы появятся на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="98c91-118">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="98c91-119">Столбцы будут обновлены только в случае добавления их в запрос.</span><span class="sxs-lookup"><span data-stu-id="98c91-119">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="98c91-120">В столбце **Новое значение** на панели критериев введите обновленное значение столбца.</span><span class="sxs-lookup"><span data-stu-id="98c91-120">In the **New Value** column of the Criteria pane, enter the update value for the column.</span></span> <span data-ttu-id="98c91-121">Вводить можно константы, имена столбцов или выражения.</span><span class="sxs-lookup"><span data-stu-id="98c91-121">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="98c91-122">Значения должны соответствовать типу данных обновляемого столбца или быть совместимыми с ним.</span><span class="sxs-lookup"><span data-stu-id="98c91-122">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="98c91-123">Конструктор запросов и представлений не может проверить, поместится ли значение в обновляемый столбец с определенной длиной.</span><span class="sxs-lookup"><span data-stu-id="98c91-123">The Query and View Designer cannot check that a value fits within the length of the column you are updating.</span></span> <span data-ttu-id="98c91-124">Слишком длинное значение может быть усечено без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="98c91-124">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="98c91-125">Например, если длина столбца `name` — 20 символов, а длина обновляемого значения — 25 символов, последние 5 символов могут быть усечены.</span><span class="sxs-lookup"><span data-stu-id="98c91-125">For example, if a `name` column is 20 characters long but you specify an update value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
5.  <span data-ttu-id="98c91-126">Задайте обновляемые строки путем ввода условий поиска в столбце **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="98c91-126">Define the rows to update by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="98c91-127">Дополнительные сведения см. в разделе [Определение критериев поиска (визуальные инструменты для баз данных)](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="98c91-127">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="98c91-128">Если условие поиска не задано, будут обновлены все строки указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="98c91-128">If you do not specify a search condition, all rows in the specified table will be updated.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="98c91-129">При добавлении столбца на панель критериев для использования в условии поиска конструктор запросов и представлений также добавит его в список обновляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="98c91-129">When you add a column to the Criteria pane for use in a search condition, the Query and View Designer also adds it to the list of columns to be updated.</span></span> <span data-ttu-id="98c91-130">Если столбец необходимо использовать в условии поиска, но не обновлять, снимите флажок рядом с именем столбца в прямоугольнике, представляющем таблицу или возвращающий табличное значение объект.</span><span class="sxs-lookup"><span data-stu-id="98c91-130">If you want to use a column for a search condition but not update it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
 <span data-ttu-id="98c91-131">При выполнении запроса на обновление в [панели результатов](results-pane-visual-database-tools.md)не выводятся никакие результаты.</span><span class="sxs-lookup"><span data-stu-id="98c91-131">When you execute an Update query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="98c91-132">Вместо этого появляется сообщение о том, сколько строк было изменено.</span><span class="sxs-lookup"><span data-stu-id="98c91-132">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c91-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="98c91-133">See Also</span></span>  
 <span data-ttu-id="98c91-134">[Поддерживаемые типы запросов &#40;визуальных инструментов для баз данных&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="98c91-134">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="98c91-135">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="98c91-135">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="98c91-136">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="98c91-136">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
