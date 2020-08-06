---
title: Создание, изменение и удаление пространственных индексов | Документация Майкрософт
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], creating
- spatial indexes [SQL Server], dropping
- spatial indexes [SQL Server], creating
- indexes [SQL Server], dropping
- indexes [SQL Server], modifying
- spatial indexes [SQL Server], modifying
ms.assetid: 00c1b927-8ec5-44cf-87c2-c8de59745735
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 88de17e8c487d9a965f2e236edac064dc2fe4c7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655572"
---
# <a name="create-modify-and-drop-spatial-indexes"></a><span data-ttu-id="ac3a7-102">Создание, изменение и удаление пространственных индексов</span><span class="sxs-lookup"><span data-stu-id="ac3a7-102">Create, Modify, and Drop Spatial Indexes</span></span>
  <span data-ttu-id="ac3a7-103">Пространственный индекс может более эффективно выполнять определенные операции над столбцом `geometry` `geography` типа данных или ( *пространственный столбец*).</span><span class="sxs-lookup"><span data-stu-id="ac3a7-103">A spatial index can more efficiently perform certain operations on a column of the `geometry` or `geography` data type (a *spatial column*).</span></span> <span data-ttu-id="ac3a7-104">Для пространственного столбца может быть задано несколько пространственных индексов.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-104">More than one spatial index can be specified on a spatial column.</span></span> <span data-ttu-id="ac3a7-105">Это целесообразно, например, при индексировании различных параметров тесселяции в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-105">This is useful, for example, for indexing different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="ac3a7-106">На создание пространственных индексов накладывается ряд ограничений.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-106">There are a number of restrictions on creating spatial indexes.</span></span> <span data-ttu-id="ac3a7-107">Дополнительные сведения см. в подразделе [Ограничения пространственных индексов](#restrictions) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-107">For more information, see [Restrictions on Spatial Indexes](#restrictions) in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac3a7-108">Дополнительные сведения о связи пространственных индексов с секциями и файловыми группами см. в подразделе "Примечания" раздела [CREATE SPATIAL INDEX (Transact-SQL)](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac3a7-108">For information about the relationship of spatial indexes to partition and to filegroups, see the "Remarks" section in [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
##  <a name="creating-modifying-and-dropping-spatial-indexes"></a><a name="creating"></a> <span data-ttu-id="ac3a7-109">Создание, изменение и удаление пространственных индексов</span><span class="sxs-lookup"><span data-stu-id="ac3a7-109">Creating, Modifying, and Dropping Spatial Indexes</span></span>  
  
###  <a name="to-create-a-spatial-index"></a><a name="create"></a> <span data-ttu-id="ac3a7-110">Создание пространственного индекса</span><span class="sxs-lookup"><span data-stu-id="ac3a7-110">To create a spatial index</span></span>  
 <span data-ttu-id="ac3a7-111">**Создание нового пространственного индекса с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ac3a7-111">**To create a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="ac3a7-112">CREATE SPATIAL INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ac3a7-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-spatial-index-transact-sql)  
  
 <span data-ttu-id="ac3a7-113">**Создание пространственного индекса с помощью диалогового окна «Создание индекса» в среде Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ac3a7-113">**To create a spatial index by using the New Index dialog box in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-management-studio"></a><span data-ttu-id="ac3a7-114">Создание пространственного индекса в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="ac3a7-114">To create a spatial index in Management Studio</span></span>  
  
1.  <span data-ttu-id="ac3a7-115">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-115">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ac3a7-116">Разверните узел **Базы данных**, разверните базу данных, содержащую таблицу с нужным индексом, а затем — узел **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-116">Expand **Databases**, expand the database that contains the table with the specified index, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="ac3a7-117">Раскройте таблицу, для которой необходимо создать индекс.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-117">Expand the table for which you want to create the index.</span></span>  
  
4.  <span data-ttu-id="ac3a7-118">Щелкните правой кнопкой мыши **Индексы** и в контекстном меню выберите команду **Создать индекс**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-118">Right-click **Indexes** and select **New Index**.</span></span>  
  
5.  <span data-ttu-id="ac3a7-119">В поле **Имя индекса** введите имя индекса.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-119">In the **Index name** field, enter a name for the index.</span></span>  
  
6.  <span data-ttu-id="ac3a7-120">В раскрывающемся списке **Тип индекса** выберите **Пространственный**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-120">In the **Index type** drop-down list, select **Spatial**.</span></span>  
  
7.  <span data-ttu-id="ac3a7-121">Чтобы указать пространственный столбец, который необходимо проиндексировать, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-121">To specify the spatial column that you want to index, click **Add**.</span></span>  
  
8.  <span data-ttu-id="ac3a7-122">В диалоговом окне **Выбор столбцов из** *\<table name>* выберите столбец типа `geometry` или установите `geography` соответствующий флажок.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-122">In the **Select Columns from** *\<table name>* dialog box, select a column of type `geometry` or `geography` by selecting the corresponding check box.</span></span> <span data-ttu-id="ac3a7-123">Остальные пространственные столбцы при этом станут недоступными для редактирования.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-123">Any other spatial columns then become uneditable.</span></span> <span data-ttu-id="ac3a7-124">Если необходимо выбрать другой пространственный столбец, то сначала нужно снять флажок со столбца, выбранного в данный момент.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-124">If you want to select a different spatial column, you must first clear the currently selected column.</span></span> <span data-ttu-id="ac3a7-125">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-125">When finished, click **OK**.</span></span>  
  
9. <span data-ttu-id="ac3a7-126">Проверьте выбор столбца в сетке **Ключевые столбцы индекса** .</span><span class="sxs-lookup"><span data-stu-id="ac3a7-126">Verify your column selection in the **Index key columns** grid.</span></span>  
  
10. <span data-ttu-id="ac3a7-127">В области **Выбор страницы** диалогового окна **Свойства индекса** щелкните **Пространственный**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-127">In the **Select a page** pane of the **Index Properties** dialog box, click **Spatial**.</span></span>  
  
11. <span data-ttu-id="ac3a7-128">На странице **Пространственный** укажите значения, которые необходимо использовать для пространственных свойств индекса.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-128">On the **Spatial** page, specify the values that you want to use for the spatial properties of the index.</span></span>  
  
     <span data-ttu-id="ac3a7-129">При создании индекса для `geometry` столбца типа необходимо указать координаты **( *`X-min`* , *`Y-min`* )** и **( *`X-max`* , *`Y-max`* )** ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-129">When creating an index on a `geometry` type column, you must specify the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="ac3a7-130">Для индекса `geography` столбца типа поля ограничивающего прямоугольника становятся доступны только для чтения после указания схемы тесселяции **географической сетки** , так как тесселяция географической сетки не использует ограничивающий прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-130">For an index on a `geography` type column, the bounding-box fields become read-only after you specify the **Geography grid** tessellation scheme, because geography grid tessellation does not use a bounding box.</span></span>  
  
     <span data-ttu-id="ac3a7-131">При необходимости можно указать нестандартные значения для поля **Число ячеек на объект** и для плотности сетки на любом уровне схемы тесселяции.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-131">Optionally, you can specify nondefault values for the **Cells Per Object** field and for the grid density at any level of the tessellation scheme.</span></span> <span data-ttu-id="ac3a7-132">По умолчанию количество ячеек на объект составляет 16 для [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] или 8 для [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] или более поздней версии, а плотность сетки — **Средняя** для [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac3a7-132">The default number of cells per object is 16 for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or 8 for [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] or higher, and the default grid density is **Medium** for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span>  
  
     <span data-ttu-id="ac3a7-133">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]можно выбрать схему тесселяции GEOMETRY_AUTO_GRID или GEOGRAPHY_AUTO_GRID.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-133">You can select GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID for tessellation scheme in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ac3a7-134">При выборе GEOMETRY_AUTO_GRID или GEOGRAPHY_AUTO_GRID параметры плотности сетки «Уровень 1», «Уровень 2», «Уровень 3» и «Уровень 4» будут отключены.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-134">When GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID is selected, then Level 1, Level 2, Level 3, and Level 4 grid density options are disabled.</span></span>  
  
     <span data-ttu-id="ac3a7-135">Дополнительные сведения об этих свойствах см. в разделе [Справка F1 свойств индекса](../indexes/index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="ac3a7-135">For more information about these properties, see [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span></span>  
  
12. <span data-ttu-id="ac3a7-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-136">Click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac3a7-137">Чтобы создать другой пространственный индекс на том же или другом пространственном столбце, повторите предыдущие шаги.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-137">To create another spatial index on the same or a different spatial column, repeat the preceding steps.</span></span>  
  
  
 <span data-ttu-id="ac3a7-138">**Создание пространственного индекса с помощью конструктора таблиц в среде Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ac3a7-138">**To create a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-table-designer"></a><span data-ttu-id="ac3a7-139">Создание пространственного индекса в конструкторе таблиц</span><span class="sxs-lookup"><span data-stu-id="ac3a7-139">To create a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="ac3a7-140">В обозревателе объектов щелкните правой кнопкой мыши таблицу, для которой нужно создать пространственный индекс, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-140">In Object Explorer, right-click the table for which you want to create a spatial index, and then click **Design**.</span></span>  
  
     <span data-ttu-id="ac3a7-141">Таблица откроется в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-141">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="ac3a7-142">Выберите столбец `geometry` или `geography` для создания индекса.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-142">Select a `geometry` or `geography` column for the index.</span></span>  
  
3.  <span data-ttu-id="ac3a7-143">В меню **Конструктор таблиц** выберите пункт **Пространственный индекс**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-143">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
4.  <span data-ttu-id="ac3a7-144">В диалоговом окне **Пространственные индексы** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-144">In the **Spatial Indexes** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="ac3a7-145">Выберите новый индекс в списке **Выбранные пространственные индексы** и в сетке справа задайте свойства пространственного индекса.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-145">Select the new index in the **Selected Spatial Index** list, and in the grid to the right, set the properties for the spatial index.</span></span> <span data-ttu-id="ac3a7-146">Дополнительные сведения о свойствах см. в разделе [Диалоговое окно "Пространственные индексы" (визуальные инструменты для баз данных)](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ac3a7-146">For information about the properties, see [Spatial Indexes Dialog Box &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
  
###  <a name="to-alter-a-spatial-index"></a><a name="alter"></a> <span data-ttu-id="ac3a7-147">Изменение пространственного индекса</span><span class="sxs-lookup"><span data-stu-id="ac3a7-147">To alter a spatial index</span></span>  
  
-   [<span data-ttu-id="ac3a7-148">ALTER INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ac3a7-148">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ac3a7-149">Чтобы изменить параметры, характерные для пространственного индекса (такие как BOUNDING_BOX или GRID), необходимо либо применить инструкцию CREATE SPATIAL INDEX с параметром DROP_EXISTING = ON, либо удалить пространственный индекс и создать новый.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-149">To change options that are specific to a spatial index, such as BOUNDING_BOX or GRID, you can either use a CREATE SPATIAL INDEX statement that specifies DROP_EXISTING = ON, or drop the spatial index and create a new one.</span></span> <span data-ttu-id="ac3a7-150">Пример см. в разделе [CREATE SPATIAL INDEX (Transact-SQL)](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac3a7-150">For an example, see [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
-   [<span data-ttu-id="ac3a7-151">Изменение индекса</span><span class="sxs-lookup"><span data-stu-id="ac3a7-151">Modify an Index</span></span>](../indexes/modify-an-index.md)  
  
-   [<span data-ttu-id="ac3a7-152">Перемещение существующего индекса в другую файловую группу</span><span class="sxs-lookup"><span data-stu-id="ac3a7-152">Move an Existing Index to a Different Filegroup</span></span>](../indexes/move-an-existing-index-to-a-different-filegroup.md)  
  
  
###  <a name="to-drop-a-spatial-index"></a><a name="drop"></a> <span data-ttu-id="ac3a7-153">Удаление пространственного индекса</span><span class="sxs-lookup"><span data-stu-id="ac3a7-153">To drop a spatial index</span></span>  
 <span data-ttu-id="ac3a7-154">**Удаление пространственного индекса с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ac3a7-154">**To drop a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="ac3a7-155">DROP INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ac3a7-155">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 <span data-ttu-id="ac3a7-156">**Удаление индекса с помощью среды Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ac3a7-156">**To drop an index by using Management Studio**</span></span>  
 [<span data-ttu-id="ac3a7-157">Удаление индекса</span><span class="sxs-lookup"><span data-stu-id="ac3a7-157">Delete an Index</span></span>](../indexes/delete-an-index.md)  
  
 <span data-ttu-id="ac3a7-158">**Удаление пространственного индекса с помощью конструктора таблиц в среде Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ac3a7-158">**To drop a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-drop-a-spatial-index-in-table-designer"></a><span data-ttu-id="ac3a7-159">Удаление пространственного индекса в конструкторе таблиц</span><span class="sxs-lookup"><span data-stu-id="ac3a7-159">To drop a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="ac3a7-160">В обозревателе объектов щелкните правой кнопкой мыши таблицу с пространственным индексом, который необходимо удалить, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-160">In Object Explorer, right-click the table with the spatial index you want to delete and click **Design**.</span></span>  
  
     <span data-ttu-id="ac3a7-161">Таблица откроется в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-161">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="ac3a7-162">В меню **Конструктор таблиц** выберите пункт **Пространственный индекс**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-162">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
     <span data-ttu-id="ac3a7-163">Откроется диалоговое окно **Пространственный индекс** .</span><span class="sxs-lookup"><span data-stu-id="ac3a7-163">The **Spatial Index** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ac3a7-164">Щелкните удаляемый индекс в столбце **Выбранные пространственные индексы** .</span><span class="sxs-lookup"><span data-stu-id="ac3a7-164">Click the index you want to delete in the **Selected Spatial Index** column.</span></span>  
  
4.  <span data-ttu-id="ac3a7-165">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-165">Click **Delete**.</span></span>  
  
  
##  <a name="restrictions-on-spatial-indexes"></a><a name="restrictions"></a> <span data-ttu-id="ac3a7-166">Ограничения пространственных индексов</span><span class="sxs-lookup"><span data-stu-id="ac3a7-166">Restrictions on Spatial Indexes</span></span>  
 <span data-ttu-id="ac3a7-167">Пространственный индекс можно создать только для столбца типа `geometry` или `geography`.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-167">A spatial index can be created only on a column of type `geometry` or `geography`.</span></span>  
  
### <a name="table-and-view-restrictions"></a><span data-ttu-id="ac3a7-168">Ограничения таблиц и представлений</span><span class="sxs-lookup"><span data-stu-id="ac3a7-168">Table and View Restrictions</span></span>  
 <span data-ttu-id="ac3a7-169">Пространственные индексы можно определить только для таблицы, у которой имеется первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-169">Spatial indexes can be defined only on a table that has a primary key.</span></span> <span data-ttu-id="ac3a7-170">Максимально допустимое число столбцов первичного ключа составляет 15.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-170">The maximum number of primary key columns on the table is 15.</span></span>  
  
 <span data-ttu-id="ac3a7-171">Размер записей ключа индекса не должен превышать 895 байт.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-171">The maximum size of index key records is 895 bytes.</span></span> <span data-ttu-id="ac3a7-172">Размеры, превышающие указанное значение, приводят к ошибке.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-172">Larger sizes raise an error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac3a7-173">Пока для таблицы определен пространственный индекс, изменить метаданные первичного ключа невозможно.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-173">Primary key metadata cannot be changed while a spatial index is defined on a table.</span></span>  
  
 <span data-ttu-id="ac3a7-174">Пространственные индексы не могут быть заданы в индексированных представлениях.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-174">Spatial indexes cannot be specified on indexed views.</span></span>  
  
### <a name="multiple-spatial-index-restrictions"></a><span data-ttu-id="ac3a7-175">Ограничения количества пространственных индексов</span><span class="sxs-lookup"><span data-stu-id="ac3a7-175">Multiple Spatial Index Restrictions</span></span>  
 <span data-ttu-id="ac3a7-176">На любом из пространственных столбцов поддерживаемой таблицы можно создать до 249 пространственных индексов.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-176">You can create up to 249 spatial indexes on any of the spatial columns in a supported table.</span></span> <span data-ttu-id="ac3a7-177">Создание нескольких пространственных индексов на одном и том же пространственном столбце может оказаться целесообразным, например, для индексации различных параметров тесселяции в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-177">Creating more than one spatial index on the same spatial column can be useful, for example, to index different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="ac3a7-178">Одновременно можно создать только один пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-178">You can create only one spatial index at a time.</span></span>  
  
### <a name="spatial-indexes-and-process-parallelism"></a><span data-ttu-id="ac3a7-179">Пространственные индексы и параллелизм процессов</span><span class="sxs-lookup"><span data-stu-id="ac3a7-179">Spatial Indexes and Process Parallelism</span></span>  
 <span data-ttu-id="ac3a7-180">Для построения индексов можно воспользоваться доступным параллелизмом процессов.</span><span class="sxs-lookup"><span data-stu-id="ac3a7-180">An index build can use available process parallelism.</span></span>  
  
### <a name="version-restrictions"></a><span data-ttu-id="ac3a7-181">Ограничения версии</span><span class="sxs-lookup"><span data-stu-id="ac3a7-181">Version Restrictions</span></span>  
 <span data-ttu-id="ac3a7-182">Пространственные тесселяции, введенные в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , не могут проходить репликацию в [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] или [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac3a7-182">Spatial tessellations introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] cannot be replicated to [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="ac3a7-183">Необходимо использовать пространственные тесселяции [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] или [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] для пространственных индексов, чтобы обеспечить обратную совместимость с базами данных [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] или [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac3a7-183">You must use [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] spatial tessellations for spatial indexes when backward compatibility with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] databases is a requirement.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="ac3a7-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac3a7-184">See Also</span></span>  
 [<span data-ttu-id="ac3a7-185">Общие сведения о пространственных индексах</span><span class="sxs-lookup"><span data-stu-id="ac3a7-185">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
  
  
