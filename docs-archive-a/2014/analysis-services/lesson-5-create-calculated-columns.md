---
title: Занятие 6. Создание вычисляемых столбцов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d126766a-5699-4e9f-8213-8c7eea0fc14e
author: minewiskan
ms.author: owend
ms.openlocfilehash: dcebf61955e230c9e61c955683b897026553cb52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658508"
---
# <a name="lesson-6-create-calculated-columns"></a><span data-ttu-id="f21ae-102">Занятие 6: Создание вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="f21ae-102">Lesson 6: Create Calculated Columns</span></span>
  <span data-ttu-id="f21ae-103">На этом занятии мы создадим новые данные в модели путем добавления вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="f21ae-103">In this lesson, you will create new data in your model by adding calculated columns.</span></span> <span data-ttu-id="f21ae-104">Вычисляемый столбец основывается на данных, которые уже существуют в модели.</span><span class="sxs-lookup"><span data-stu-id="f21ae-104">A calculated column is based on data that already exists in the model.</span></span> <span data-ttu-id="f21ae-105">Дополнительные сведения см. в разделе [Вычисляемые столбцы (табличные службы SSAS)](tabular-models/ssas-calculated-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f21ae-105">To learn more, see [Calculated Columns &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns.md).</span></span>  
  
 <span data-ttu-id="f21ae-106">Вы создадите пять вычисляемых столбцов в трех разных таблицах.</span><span class="sxs-lookup"><span data-stu-id="f21ae-106">You will create five new calculated columns in three different tables.</span></span> <span data-ttu-id="f21ae-107">Шаги выполнения для каждой задачи могут немного отличаться друг от друга.</span><span class="sxs-lookup"><span data-stu-id="f21ae-107">The steps are slightly different for each task.</span></span> <span data-ttu-id="f21ae-108">Это сделано для того, чтобы продемонстрировать разные способы создания новых столбцов, переименовывания и размещения в разных местах в таблице.</span><span class="sxs-lookup"><span data-stu-id="f21ae-108">This is to show you there are several ways to create new columns, rename them, and place them in various locations in a table.</span></span>  
  
 <span data-ttu-id="f21ae-109">Предполагаемое время выполнения этого занятия: **15 минут**</span><span class="sxs-lookup"><span data-stu-id="f21ae-109">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f21ae-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f21ae-110">Prerequisites</span></span>  
 <span data-ttu-id="f21ae-111">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="f21ae-111">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="f21ae-112">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее [Занятие 5. Создание связей](lesson-4-create-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f21ae-112">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 5: Create Relationships](lesson-4-create-relationships.md).</span></span>  
  
## <a name="create-calculated-columns"></a><span data-ttu-id="f21ae-113">Создание вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="f21ae-113">Create Calculated Columns</span></span>  
  
#### <a name="create-a-month-calendar-calculated-column-in-the-date-table"></a><span data-ttu-id="f21ae-114">Создание вычисляемого столбца «Месячный календарь» в таблице «Дата»</span><span class="sxs-lookup"><span data-stu-id="f21ae-114">Create a Month Calendar calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="f21ae-115">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]в меню **Модель** наведите указатель на пункт **Представление модели**и выберите пункт **Представление данных**.</span><span class="sxs-lookup"><span data-stu-id="f21ae-115">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Model View**, and then click **Data View**.</span></span>  
  
     <span data-ttu-id="f21ae-116">Вычисляемые столбцы можно создавать только с помощью конструктора моделей в представлении данных.</span><span class="sxs-lookup"><span data-stu-id="f21ae-116">Calculated columns can only be created by using the model designer in Data View.</span></span>  
  
2.  <span data-ttu-id="f21ae-117">В конструкторе моделей щелкните таблицу (вкладку) **Дата** .</span><span class="sxs-lookup"><span data-stu-id="f21ae-117">In the model designer, click the **Date** table (tab).</span></span>  
  
3.  <span data-ttu-id="f21ae-118">Щелкните правой кнопкой мыши столбец **календарный квартал** и выберите команду **Вставить столбец**.</span><span class="sxs-lookup"><span data-stu-id="f21ae-118">Right-click the **Calendar Quarter** column, and then click **Insert Column**.</span></span>  
  
     <span data-ttu-id="f21ae-119">В левой части столбца **календарный квартал** вставляется новый столбец с именем **: CalculatedColumn1** .</span><span class="sxs-lookup"><span data-stu-id="f21ae-119">A new column named **CalculatedColumn1** is inserted to the left of the **Calendar Quarter** column.</span></span>  
  
4.  <span data-ttu-id="f21ae-120">В строке формул над таблицей введите следующую формулу.</span><span class="sxs-lookup"><span data-stu-id="f21ae-120">In the formula bar above the table, type the following formula.</span></span> <span data-ttu-id="f21ae-121">Компонент автозаполнения помогает вводить полные имена столбцов и таблиц и выводит список доступных функций.</span><span class="sxs-lookup"><span data-stu-id="f21ae-121">AutoComplete helps you type the fully qualified names of columns and tables, and lists the functions that are available.</span></span>  
  
     `=RIGHT(" " & FORMAT([Month],"#0"), 2) & " - " & [Month Name]`  
  
     <span data-ttu-id="f21ae-122">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f21ae-122">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="f21ae-123">После этого все строки в вычисляемом столбце заполняются значениями.</span><span class="sxs-lookup"><span data-stu-id="f21ae-123">Values are then populated for all the rows in the calculated column.</span></span> <span data-ttu-id="f21ae-124">Если прокрутить содержимое таблицы вниз, вы увидите, что строки могут содержать разные значения для этого столбца, в зависимости от данных в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="f21ae-124">If you scroll down through the table, you will see that rows can have different values for this column, based on the data that is in each row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f21ae-125">При получении ошибки убедитесь в том, что имена столбцов в формуле соответствуют именам столбцов, которые были изменены в ходе выполнения задания в [занятии 3: переименование столбцов](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="f21ae-125">If you receive an error, verify the column names in the formula match the column names you changed in [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
5.  <span data-ttu-id="f21ae-126">Переименуйте этот столбец в `Month Calendar` .</span><span class="sxs-lookup"><span data-stu-id="f21ae-126">Rename this column to `Month Calendar`.</span></span>  
  
 <span data-ttu-id="f21ae-127">Вычисляемый столбец «Месячный календарь» содержит сортируемое имя для месяца.</span><span class="sxs-lookup"><span data-stu-id="f21ae-127">The Month Calendar calculated column provides a sortable name for Month.</span></span>  
  
#### <a name="create-a-day-of-week-calculated-column-in-the-date-table"></a><span data-ttu-id="f21ae-128">Создание вычисляемого столбца «День недели» в таблице «Дата»</span><span class="sxs-lookup"><span data-stu-id="f21ae-128">Create a Day of Week calculated column in the Date table</span></span>  
  
1.  <span data-ttu-id="f21ae-129">В активной таблице **Дата** щелкните меню **Столбец** и выберите команду **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="f21ae-129">With the **Date** table still active, click on the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="f21ae-130">Новый столбец будет добавлен на самой правой стороне таблицы.</span><span class="sxs-lookup"><span data-stu-id="f21ae-130">A new column is added to the far right of the table</span></span>  
  
2.  <span data-ttu-id="f21ae-131">В строке формул введите следующую формулу:</span><span class="sxs-lookup"><span data-stu-id="f21ae-131">In the formula bar, type the following formula:</span></span>  
  
     `=RIGHT(" " & FORMAT([Day Number Of Week],"#0"), 2) & " - " & [Day Name]`  
  
     <span data-ttu-id="f21ae-132">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f21ae-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="f21ae-133">Переименуйте столбец в `Day of Week` .</span><span class="sxs-lookup"><span data-stu-id="f21ae-133">Rename the column to `Day of Week`.</span></span>  
  
4.  <span data-ttu-id="f21ae-134">Щелкните заголовок столбца и перетащите столбец между столбцами **Название дня** и **День месяца** .</span><span class="sxs-lookup"><span data-stu-id="f21ae-134">Click on the column heading, and then drag the column between the **Day Name** column and the **Day of Month** column.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f21ae-135">Перемещение столбцов в таблице облегчает навигацию.</span><span class="sxs-lookup"><span data-stu-id="f21ae-135">Moving columns in your table makes it easier to navigate.</span></span>  
  
 <span data-ttu-id="f21ae-136">Вычисляемый столбец «День недели» содержит сортируемое имя дня недели.</span><span class="sxs-lookup"><span data-stu-id="f21ae-136">The Day of Week calculated column provides a sortable name for the day of week.</span></span>  
  
#### <a name="create-a-product-subcategory-name-calculated-column-in-the-product-table"></a><span data-ttu-id="f21ae-137">Создание вычисляемого столбца «Имя подкатегории продуктов» в таблице «Продукт»</span><span class="sxs-lookup"><span data-stu-id="f21ae-137">Create a Product Subcategory Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="f21ae-138">Выберите таблицу **Продукт** в конструкторе моделей.</span><span class="sxs-lookup"><span data-stu-id="f21ae-138">In the model designer, select the **Product** table.</span></span>  
  
2.  <span data-ttu-id="f21ae-139">Прокрутите до правого края таблицы.</span><span class="sxs-lookup"><span data-stu-id="f21ae-139">Scroll to the far right of the table.</span></span> <span data-ttu-id="f21ae-140">Найдите крайний правый столбец с именем **Добавить столбец** (курсивом) и щелкните его заголовок.</span><span class="sxs-lookup"><span data-stu-id="f21ae-140">Notice the right-most column is named **Add Column** (italicized), click the column heading.</span></span>  
  
3.  <span data-ttu-id="f21ae-141">В строке формул введите следующую формулу:</span><span class="sxs-lookup"><span data-stu-id="f21ae-141">In the formula bar, type the following formula.</span></span>  
  
     `=RELATED('Product Subcategory'[Product Subcategory Name])`  
  
     <span data-ttu-id="f21ae-142">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f21ae-142">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="f21ae-143">Переименуйте столбец в `Product Subcategory Name` .</span><span class="sxs-lookup"><span data-stu-id="f21ae-143">Rename the column to `Product Subcategory Name`.</span></span>  
  
 <span data-ttu-id="f21ae-144">Вычисляемый столбец «Имя подкатегории продуктов» используется для создания иерархии в таблице «Продукт», которая включает данные из столбца «Имя подкатегории продуктов» в таблице «Подкатегория продуктов».</span><span class="sxs-lookup"><span data-stu-id="f21ae-144">The Product Subcategory Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Subcategory Name column in the Product Subcategory table.</span></span> <span data-ttu-id="f21ae-145">Иерархии не могут охватывать более одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="f21ae-145">Hierarchies cannot span more than one table.</span></span> <span data-ttu-id="f21ae-146">Иерархии будут созданы позднее, в занятии 7.</span><span class="sxs-lookup"><span data-stu-id="f21ae-146">You will create hierarchies later in Lesson 7.</span></span>  
  
#### <a name="create-a-product-category-name-calculated-column-in-the-product-table"></a><span data-ttu-id="f21ae-147">Создание вычисляемого столбца «Имя категории продуктов» в таблице «Продукт»</span><span class="sxs-lookup"><span data-stu-id="f21ae-147">Create a Product Category Name calculated column in the Product table</span></span>  
  
1.  <span data-ttu-id="f21ae-148">При выбранной таблице **Продукт** откройте меню **Столбец** и выберите команду **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="f21ae-148">With the **Product** table still active, click the **Column** menu, and then click **Add Column**.</span></span>  
  
2.  <span data-ttu-id="f21ae-149">В строке формул введите следующую формулу:</span><span class="sxs-lookup"><span data-stu-id="f21ae-149">In the formula bar, type the following formula:</span></span>  
  
     `=RELATED('Product Category'[Product Category Name])`  
  
     <span data-ttu-id="f21ae-150">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f21ae-150">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="f21ae-151">Переименуйте столбец в `Product Category Name` .</span><span class="sxs-lookup"><span data-stu-id="f21ae-151">Rename the column to `Product Category Name`.</span></span>  
  
 <span data-ttu-id="f21ae-152">Вычисляемый столбец «Имя категории продуктов» используется для создания иерархии в таблице «Продукт», которая включает данные из столбца «Имя категории продуктов» в таблице «Категория продуктов».</span><span class="sxs-lookup"><span data-stu-id="f21ae-152">The Product Category Name calculated column is used to create a hierarchy in the Product table which includes data from the Product Category Name column in the Product Category table.</span></span> <span data-ttu-id="f21ae-153">Иерархии не могут охватывать более одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="f21ae-153">Hierarchies cannot span more than one table.</span></span>  
  
#### <a name="create-a-margin-calculated-column-in-the-internet-sales-table"></a><span data-ttu-id="f21ae-154">Создание вычисляемого столбца «Маржа» в таблице «Интернет-продажи»</span><span class="sxs-lookup"><span data-stu-id="f21ae-154">Create a Margin calculated column in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="f21ae-155">Выберите таблицу **Интернет-продажи** в конструкторе моделей.</span><span class="sxs-lookup"><span data-stu-id="f21ae-155">In the model designer, select the **Internet Sales** table.</span></span>  
  
2.  <span data-ttu-id="f21ae-156">Добавление нового столбца.</span><span class="sxs-lookup"><span data-stu-id="f21ae-156">Add a new column.</span></span>  
  
3.  <span data-ttu-id="f21ae-157">В строке формул введите следующую формулу:</span><span class="sxs-lookup"><span data-stu-id="f21ae-157">In the formula bar, type the following formula:</span></span>  
  
     `=[Sales Amount]-[Total Product Cost]`  
  
     <span data-ttu-id="f21ae-158">Завершив построение формулы, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f21ae-158">When you have finished building the formula, press ENTER.</span></span>  
  
4.  <span data-ttu-id="f21ae-159">Переименуйте столбец в `Margin` .</span><span class="sxs-lookup"><span data-stu-id="f21ae-159">Rename the column to `Margin`.</span></span>  
  
5.  <span data-ttu-id="f21ae-160">Перетащите столбец между столбцами **Сумма продаж** и **Сумма налога** .</span><span class="sxs-lookup"><span data-stu-id="f21ae-160">Drag the column between the **Sales Amount** column and the **Tax Amt** column.</span></span>  
  
 <span data-ttu-id="f21ae-161">Вычисляемый столбец «Маржа» используется для анализа маржи для каждой строки (продукта).</span><span class="sxs-lookup"><span data-stu-id="f21ae-161">The Margin calculated column is used to analyze profit margins for each (product) row.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f21ae-162">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="f21ae-162">Next Step</span></span>  
 <span data-ttu-id="f21ae-163">Чтобы продолжить изучение этого занятия, перейдите к следующему занятию: [Занятие 7. Создание мер](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="f21ae-163">To continue this lesson, go to the next lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
  
