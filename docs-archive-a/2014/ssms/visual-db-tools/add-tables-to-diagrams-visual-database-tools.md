---
title: Добавление таблиц в диаграммы (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
ms.assetid: 5440fdf7-ac04-4325-9f32-181f4cd402e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe5c1274ac390f4834bd8ac1088258061fc0406d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664654"
---
# <a name="add-tables-to-diagrams-visual-database-tools"></a><span data-ttu-id="b6ecb-102">Добавление таблиц в диаграммы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b6ecb-102">Add Tables to Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="b6ecb-103">Можно добавить таблицу в диаграмму базы данных, чтобы изменить структуру этой таблицы или связать ее с другими таблицами.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-103">You can add a table to your database diagram to edit its structure or relate it to other tables in your diagram.</span></span> <span data-ttu-id="b6ecb-104">В диаграмму можно добавлять существующие таблицы или вставлять новые, еще не определенные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-104">You can either add existing database tables to a diagram or insert a new table that has not yet been defined in the database.</span></span>  
  
### <a name="to-insert-a-new-table-into-a-diagram"></a><span data-ttu-id="b6ecb-105">Вставка новой таблицы в диаграмму</span><span class="sxs-lookup"><span data-stu-id="b6ecb-105">To insert a new table into a diagram</span></span>  
  
1.  <span data-ttu-id="b6ecb-106">Убедитесь, что осуществлено подключение к базе данных, в которой требуется создать таблицу.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-106">Make sure you are connected to the database in which you want to create the table.</span></span>  
  
     <span data-ttu-id="b6ecb-107">Чтобы создать таблицу в текущей диаграмме, нажмите на панели инструментов кнопку **Создать таблицу** .</span><span class="sxs-lookup"><span data-stu-id="b6ecb-107">To create a table in your current diagram, click the **New Table** button on the toolbar.</span></span>  
  
     <span data-ttu-id="b6ecb-108">-или-</span><span class="sxs-lookup"><span data-stu-id="b6ecb-108">-or-</span></span>  
  
     <span data-ttu-id="b6ecb-109">Щелкните правой кнопкой мыши диаграмму и выберите пункт **Создать таблицу**.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-109">Right-click in the diagram and select **New Table**.</span></span>  
  
2.  <span data-ttu-id="b6ecb-110">Измените или сохраните имя таблицы, назначенное системой, в диалоговом окне **Выбор имени** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-110">Modify or accept the system-assigned table name, in the **Choose Name** dialog box, and then choose **OK**.</span></span>  
  
     <span data-ttu-id="b6ecb-111">Новая таблица появится в диаграмме в стандартном представлении.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-111">A new table appears in the diagram in Standard view.</span></span>  
  
3.  <span data-ttu-id="b6ecb-112">В первую ячейку новой таблицы введите имя столбца.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-112">In the first cell of the new table, type a column name.</span></span> <span data-ttu-id="b6ecb-113">Затем нажмите клавишу TAB, чтобы перейти к следующей ячейке.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-113">Then press the TAB key to move to the next cell.</span></span>  
  
4.  <span data-ttu-id="b6ecb-114">Выберите новый тип данных для столбца из списка **Тип данных**.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-114">Under **Data Type**, select a data type for the column.</span></span> <span data-ttu-id="b6ecb-115">У каждого столбца должны быть название и тип данных.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-115">Each column must have a name and data type.</span></span>  
  
     <span data-ttu-id="b6ecb-116">Остальные свойства столбца можно задать в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-116">You can set the column's other properties in Table Designer.</span></span>  
  
5.  <span data-ttu-id="b6ecb-117">Повторите шаги 3 и 4 для каждого столбца, который нужно добавить в таблицу.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-117">Repeat steps 3 and 4 for each column you want to add to the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6ecb-118">При сохранении диаграммы базы данных новая таблица будет добавлена в базу данных.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-118">When you save your database diagram, the new table will be added to your database.</span></span>  
  
### <a name="to-add-an-existing-table-to-a-diagram"></a><span data-ttu-id="b6ecb-119">Добавление существующей таблицы в диаграмму</span><span class="sxs-lookup"><span data-stu-id="b6ecb-119">To add an existing table to a diagram</span></span>  
  
1.  <span data-ttu-id="b6ecb-120">Убедитесь, что осуществлено подключение к той базе данных, таблицы которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-120">Make sure you are connected to the database whose tables you want to edit.</span></span>  
  
2.  <span data-ttu-id="b6ecb-121">Выберите таблицу в папке **Таблицы** .</span><span class="sxs-lookup"><span data-stu-id="b6ecb-121">Select a table in the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b6ecb-122">Перетащите таблицу в диаграмму базы данных.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-122">Drag the table into your database diagram.</span></span>  
  
4.  <span data-ttu-id="b6ecb-123">Отпустите кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-123">Release the mouse button.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6ecb-124">Чтобы отобразить отношения между выбранной таблицей и другими таблицами, в диаграмме автоматически рисуются линии связей.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-124">If relationships exist between the selected table and other tables in your diagram, relationship lines are automatically drawn.</span></span>  
  
### <a name="to-add-related-tables-to-a-diagram"></a><span data-ttu-id="b6ecb-125">Добавление связанных таблиц в диаграмму</span><span class="sxs-lookup"><span data-stu-id="b6ecb-125">To add related tables to a diagram</span></span>  
  
1.  <span data-ttu-id="b6ecb-126">Выберите на диаграмме базы данных одну или несколько таблиц с ограничениями внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-126">Select one or more tables with foreign key constraints in the database diagram.</span></span>  
  
2.  <span data-ttu-id="b6ecb-127">Щелкните правой кнопкой мыши любую из выбранных таблиц и выберите **Добавить связанные таблицы**.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-127">Right-click any of the selected tables and choose **Add Related Tables**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6ecb-128">В диаграмму добавляются и таблицы, на которые ссылается ограничение внешнего ключа из выбранных таблиц, и таблицы, которые ссылаются на выбранные таблицы по ограничению внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="b6ecb-128">Both those tables referenced by a foreign key constraint from the selected table(s) and those referencing the selected table(s) with a foreign key constraint are added to the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ecb-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="b6ecb-129">See Also</span></span>  
 <span data-ttu-id="b6ecb-130">[Работа с диаграммами баз данных &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b6ecb-130">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="b6ecb-131">Работа с таблицами в диаграммах базы данных (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b6ecb-131">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
