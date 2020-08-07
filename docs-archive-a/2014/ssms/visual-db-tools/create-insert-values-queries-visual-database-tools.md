---
title: Создание запросов на вставку значений (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting values
- queries [SQL Server], types
- adding values
- row additions [SQL Server], Insert Values query
- inserting rows
- Insert Values query
- adding rows
- table values [SQL Server]
ms.assetid: 2d4b2f6d-cc09-434b-8a0e-ccce40628064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fc71b0148ee8a7e92c517fe75b56c329b3c88f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731282"
---
# <a name="create-insert-values-queries-visual-database-tools"></a><span data-ttu-id="4ed90-102">Создание запросов на вставку значений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="4ed90-102">Create Insert Values Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="4ed90-103">Добавить новую строку в текущую таблицу можно с помощью запроса «Вставка значений».</span><span class="sxs-lookup"><span data-stu-id="4ed90-103">You can create a new row in the current table using an Insert Values query.</span></span> <span data-ttu-id="4ed90-104">При создании запроса «Вставка значений» необходимо указать:</span><span class="sxs-lookup"><span data-stu-id="4ed90-104">When you create an Insert Values query, you specify:</span></span>  
  
-   <span data-ttu-id="4ed90-105">таблицу базы данных, в которую добавляется запись;</span><span class="sxs-lookup"><span data-stu-id="4ed90-105">The database table to add the row to.</span></span>  
  
-   <span data-ttu-id="4ed90-106">столбцы, содержимое которых нужно добавить;</span><span class="sxs-lookup"><span data-stu-id="4ed90-106">The columns whose contents you want to add.</span></span>  
  
-   <span data-ttu-id="4ed90-107">константу или выражение, значение которой нужно вставить в соответствующий столбец.</span><span class="sxs-lookup"><span data-stu-id="4ed90-107">The value or expression to insert into the individual columns.</span></span>  
  
 <span data-ttu-id="4ed90-108">Например, следующий запрос добавляет запись в таблицу `titles` , указывая значения столбцов для столбцов title, type, publisher и price:</span><span class="sxs-lookup"><span data-stu-id="4ed90-108">For example, the following query adds a row to the `titles` table, specifying values for the title, type, publisher, and price:</span></span>  
  
```  
INSERT INTO titles  
         (title_id, title, type, pub_id, price)  
VALUES   ('BU9876', 'Creating Web Pages', 'business', '1389', '29.99')  
```  
  
 <span data-ttu-id="4ed90-109">При создании запроса «Вставка значений» панель критериев изменяется, показывая только те параметры, которые доступны при добавлении записей: имя столбца и значение для вставки.</span><span class="sxs-lookup"><span data-stu-id="4ed90-109">When you create an Insert Values query, the Criteria pane changes to reflect the only options available for inserting a new row: the column name and the value to insert.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4ed90-110">Действия, произведенные при выполнении запроса «Вставка значений», отменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="4ed90-110">You cannot undo the action of executing an Insert Values query.</span></span> <span data-ttu-id="4ed90-111">В целях предосторожности создайте резервную копию данных перед выполнением запроса.</span><span class="sxs-lookup"><span data-stu-id="4ed90-111">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-values-query"></a><span data-ttu-id="4ed90-112">Создание запроса «Вставка значений»</span><span class="sxs-lookup"><span data-stu-id="4ed90-112">To create an Insert Values query</span></span>  
  
1.  <span data-ttu-id="4ed90-113">Добавьте таблицу, которую требуется обновить, на панель диаграмм.</span><span class="sxs-lookup"><span data-stu-id="4ed90-113">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="4ed90-114">В меню **Конструктор запросов** выберите **Изменить тип**и щелкните **Вставить значения**.</span><span class="sxs-lookup"><span data-stu-id="4ed90-114">From the **Query Designer** menu point to **Change Type**, and then click **Insert Values**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ed90-115">Если во время создания запроса "вставка значений" на панели диаграммы отображается несколько таблиц, в конструкторе запросов и представлений появляется диалоговое окно [Выберите целевую таблицу для Insert Values](visual-database-tools.md) , в котором пользователь должен указать имя обновляемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="4ed90-115">If more than one table is displayed in the Diagram pane when you start the Insert Values query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="4ed90-116">На панели диаграмм установите флажки рядом с каждым столбцом, для которого необходимо обновить значения.</span><span class="sxs-lookup"><span data-stu-id="4ed90-116">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="4ed90-117">Эти столбцы появятся на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="4ed90-117">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="4ed90-118">Столбцы будут обновлены только в случае добавления их в запрос.</span><span class="sxs-lookup"><span data-stu-id="4ed90-118">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="4ed90-119">В столбце **Новое значение** на панели критериев введите новое значение столбца.</span><span class="sxs-lookup"><span data-stu-id="4ed90-119">In the **New Value** column of the Criteria pane, enter the new value for the column.</span></span> <span data-ttu-id="4ed90-120">Вводить можно константы, имена столбцов или выражения.</span><span class="sxs-lookup"><span data-stu-id="4ed90-120">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="4ed90-121">Значения должны соответствовать типу данных обновляемого столбца или быть совместимыми с ним.</span><span class="sxs-lookup"><span data-stu-id="4ed90-121">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="4ed90-122">Конструктор запросов и представлений не в состоянии проверить, соответствует ли длина вставляемого значения длине соответствующего поля таблицы.</span><span class="sxs-lookup"><span data-stu-id="4ed90-122">The Query and View Designer cannot check that a value fits within the length of the column you are inserting.</span></span> <span data-ttu-id="4ed90-123">Слишком длинное значение может быть усечено без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4ed90-123">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="4ed90-124">Например, если длина столбца `name` равна 20 символам, при попытке поместить туда значение длиной 25 символов произойдет усечение последних 5 символов.</span><span class="sxs-lookup"><span data-stu-id="4ed90-124">For example, if a `name` column is 20 characters long but you specify an insert value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
 <span data-ttu-id="4ed90-125">При выполнении запроса "вставка значений" панель [Результаты](results-pane-visual-database-tools.md)не отображает никаких сообщений.</span><span class="sxs-lookup"><span data-stu-id="4ed90-125">When you execute an Insert Values query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="4ed90-126">Вместо этого появляется сообщение о том, сколько строк было изменено.</span><span class="sxs-lookup"><span data-stu-id="4ed90-126">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed90-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ed90-127">See Also</span></span>  
 <span data-ttu-id="4ed90-128">[Поддерживаемые типы запросов &#40;визуальных инструментов для баз данных&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4ed90-128">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="4ed90-129">[Разделы руководства по проектированию запросов и представлений &#40;визуальных инструментов для баз данных&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4ed90-129">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4ed90-130">Выполнение основных операций с запросами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="4ed90-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
