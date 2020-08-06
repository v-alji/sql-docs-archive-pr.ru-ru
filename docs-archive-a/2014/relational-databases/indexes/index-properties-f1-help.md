---
title: Справка F1 для свойств индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.storage.f1
- sql12.swb.indexproperties.columns.f1
- sql12.swb.indexproperties.partitions.f1
- sql12.swb.indexproperties.general.f1
- sql12.swb.indexproperties.filter.f1
- sql12.swb.indexproperties.options.f1
- sql12.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 390a63d21dc72e052017f2d30b061d71de863bc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750940"
---
# <a name="index-properties-f1-help"></a><span data-ttu-id="693b9-102">Справка F1 свойств индекса</span><span class="sxs-lookup"><span data-stu-id="693b9-102">Index Properties F1 Help</span></span>
  <span data-ttu-id="693b9-103">Подразделы этого раздела посвящены различным свойствам индекса, доступным в диалоговых окнах среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="693b9-103">The sections in this topic refer to various index properties that are available by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialogs.</span></span>  
  
 <span data-ttu-id="693b9-104">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="693b9-104">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="693b9-105">Свойства индекса (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="693b9-105">Index Properties General Page</span></span>](#General)  
  
 [<span data-ttu-id="693b9-106">Диалоговое окно «Выбор столбцов (индекса)»</span><span class="sxs-lookup"><span data-stu-id="693b9-106">Select (Index) Columns Dialog Box</span></span>](#Columns)  
  
 [<span data-ttu-id="693b9-107">Свойства индекса (страница «Хранение»)</span><span class="sxs-lookup"><span data-stu-id="693b9-107">Index Properties Storage Page</span></span>](#Storage)  
  
 [<span data-ttu-id="693b9-108">Свойства индекса (страница «Пространственный»)</span><span class="sxs-lookup"><span data-stu-id="693b9-108">Index Properties Spatial Page</span></span>](#Spatial)  
  
 [<span data-ttu-id="693b9-109">Свойства индекса (страница «Фильтр»)</span><span class="sxs-lookup"><span data-stu-id="693b9-109">Index Properties Filter Page</span></span>](#Filter)  
  
##  <a name="index-properties-general-page"></a><a name="General"></a> <span data-ttu-id="693b9-110">Свойства индекса (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="693b9-110">Index Properties General Page</span></span>  
 <span data-ttu-id="693b9-111">Страница «Общие» используется для просмотра или изменения свойств индекса выбранной таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="693b9-111">Use the General page to view or modify index properties for the selected table or view.</span></span> <span data-ttu-id="693b9-112">Параметры для каждой страницы могут изменяться в зависимости от типа выбранного индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-112">The options for each page may change based on the type of index selected.</span></span>  
  
 <span data-ttu-id="693b9-113">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="693b9-113">**Table name**</span></span>  
 <span data-ttu-id="693b9-114">Отображает имя таблицы или представления, для которых был создан индекс.</span><span class="sxs-lookup"><span data-stu-id="693b9-114">Displays the name of the table or view that the index was created on.</span></span> <span data-ttu-id="693b9-115">Это поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="693b9-115">This field is read-only.</span></span> <span data-ttu-id="693b9-116">Чтобы выбрать другую таблицу, закройте страницу «Свойства индекса», выберите требуемую таблицу и снова откройте страницу «Свойства индекса».</span><span class="sxs-lookup"><span data-stu-id="693b9-116">To select a different table, close the Index Properties page, select the correct table, and then open the Index Properties page again.</span></span>  
  
 <span data-ttu-id="693b9-117">Пространственные индексы не могут быть заданы в индексированных представлениях.</span><span class="sxs-lookup"><span data-stu-id="693b9-117">Spatial indexes cannot be specified on indexed views.</span></span> <span data-ttu-id="693b9-118">Пространственные индексы могут быть определены только для таблицы с первичным ключом.</span><span class="sxs-lookup"><span data-stu-id="693b9-118">Spatial indexes can be defined only for a table that has a primary key.</span></span> <span data-ttu-id="693b9-119">Максимально допустимое число столбцов первичного ключа составляет 15.</span><span class="sxs-lookup"><span data-stu-id="693b9-119">The maximum number of primary key columns on the table is 15.</span></span> <span data-ttu-id="693b9-120">Общий размер столбцов первичного ключа в строке не может превышать 895 байт.</span><span class="sxs-lookup"><span data-stu-id="693b9-120">The combined per-row size of the primary-key columns is limited to a maximum of 895 bytes.</span></span>  
  
 <span data-ttu-id="693b9-121">**Имя индекса**</span><span class="sxs-lookup"><span data-stu-id="693b9-121">**Index name**</span></span>  
 <span data-ttu-id="693b9-122">Отображает имя индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-122">Displays the name of the index.</span></span> <span data-ttu-id="693b9-123">Для существующего индекса это поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="693b9-123">This field is read-only for an existing index.</span></span> <span data-ttu-id="693b9-124">При создании нового индекса введите его имя.</span><span class="sxs-lookup"><span data-stu-id="693b9-124">When creating a new index, type the name of the index.</span></span>  
  
 <span data-ttu-id="693b9-125">**Тип индекса**</span><span class="sxs-lookup"><span data-stu-id="693b9-125">**Index type**</span></span>  
 <span data-ttu-id="693b9-126">Указывает тип индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-126">Indicates the type of index.</span></span> <span data-ttu-id="693b9-127">Для новых индексов указывается тип индекса, выбранного при открытии диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="693b9-127">For new indexes, indicates the type of index selected when opening the dialog box.</span></span> <span data-ttu-id="693b9-128">Возможные индексы: **кластеризованный**, **некластеризованный**, **первичный XML**, **вторичный XML**, **пространственный**, **кластеризованный columnstore** или **некластеризованный columnstore**.</span><span class="sxs-lookup"><span data-stu-id="693b9-128">Indexes can be: **Clustered**, **Nonclustered**, **Primary XML**, **Secondary XML**, **Spatial**, **Clustered columnstore**, or **Nonclustered Columnstore**.</span></span>  
  
 <span data-ttu-id="693b9-129">**Примечание.** Для таблицы можно использовать только один кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="693b9-129">**Note** Only one clustered index is allowed for each table.</span></span> <span data-ttu-id="693b9-130">Для каждой таблицы можно использовать только один индекс Columnstore, оптимизированный для памяти xVelocity.</span><span class="sxs-lookup"><span data-stu-id="693b9-130">Only one xVelocity memory optimized columnstore index is allowed for each table.</span></span>  
  
 <span data-ttu-id="693b9-131">**Уникальный**</span><span class="sxs-lookup"><span data-stu-id="693b9-131">**Unique**</span></span>  
 <span data-ttu-id="693b9-132">Установите этот флажок, чтобы сделать индекс уникальным.</span><span class="sxs-lookup"><span data-stu-id="693b9-132">Selecting this check box makes the index unique.</span></span> <span data-ttu-id="693b9-133">Одна строка может иметь только одно значение индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-133">No two rows are permitted to have the same index value.</span></span> <span data-ttu-id="693b9-134">По умолчанию этот флажок снят.</span><span class="sxs-lookup"><span data-stu-id="693b9-134">By default, this check box is cleared.</span></span> <span data-ttu-id="693b9-135">При изменении существующего индекса в случае, если две строки имеют одинаковое значение, индекс не будет создан.</span><span class="sxs-lookup"><span data-stu-id="693b9-135">When modifying an existing index, index creation will fail if two rows have the same value.</span></span> <span data-ttu-id="693b9-136">Для столбцов с разрешенным значением NULL уникальный индекс допускает одно значение NULL.</span><span class="sxs-lookup"><span data-stu-id="693b9-136">For columns where NULL is permitted, a unique index permits one NULL value.</span></span>  
  
 <span data-ttu-id="693b9-137">Если выбран **пространственный** в поле **Тип индекса** , то флажок **уникальный** становится недоступными для выбора.</span><span class="sxs-lookup"><span data-stu-id="693b9-137">If you select **Spatial** in the **Index type** field, the **Unique** check box is dimmed.</span></span>  
  
 <span data-ttu-id="693b9-138">**ключевые столбцы индекса**</span><span class="sxs-lookup"><span data-stu-id="693b9-138">**Index key columns**</span></span>  
 <span data-ttu-id="693b9-139">Добавьте необходимые столбцы в сетку **Ключевые столбцы индекса** .</span><span class="sxs-lookup"><span data-stu-id="693b9-139">Add the desired columns to the **Index key columns** grid.</span></span> <span data-ttu-id="693b9-140">При добавлении нескольких столбцов их необходимо разместить в требуемом порядке.</span><span class="sxs-lookup"><span data-stu-id="693b9-140">When more than one column is added, the columns must be listed in the order desired.</span></span> <span data-ttu-id="693b9-141">Порядок столбцов в индексе оказывает значительное влияние на производительность операций с индексами.</span><span class="sxs-lookup"><span data-stu-id="693b9-141">The column order in an index can have a great impact on the index performance.</span></span>  
  
 <span data-ttu-id="693b9-142">Отдельный составной индекс может включать не более 16 столбцов.</span><span class="sxs-lookup"><span data-stu-id="693b9-142">No more than 16 columns can participate in a single composite index.</span></span> <span data-ttu-id="693b9-143">Если количество столбцов превышает 16, см. включенные столбцы в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="693b9-143">For greater than 16 columns, see included columns at the end of this topic.</span></span>  
  
 <span data-ttu-id="693b9-144">Пространственный индекс может быть определен только для одного столбца, который содержит пространственный тип данных ( *пространственный столбец*).</span><span class="sxs-lookup"><span data-stu-id="693b9-144">A spatial index can be defined only on a single column that contains a spatial data type (a *spatial column*).</span></span>  
  
 <span data-ttu-id="693b9-145">**имя**;</span><span class="sxs-lookup"><span data-stu-id="693b9-145">**Name**</span></span>  
 <span data-ttu-id="693b9-146">Отображает имя столбца, входящего в состав ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-146">Displays the name of the column that participates in the index key.</span></span>  
  
 <span data-ttu-id="693b9-147">**Порядок сортировки**</span><span class="sxs-lookup"><span data-stu-id="693b9-147">**Sort Order**</span></span>  
 <span data-ttu-id="693b9-148">Указывает порядок сортировки выбранного ключевого столбца — **По возрастанию** или **По убыванию**.</span><span class="sxs-lookup"><span data-stu-id="693b9-148">Specifies the sort direction of the selected index column, either **Ascending** or **Descending**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="693b9-149">Если тип индекса — **первичный XML** или **пространственный**, то этот столбец не отображается в странице.</span><span class="sxs-lookup"><span data-stu-id="693b9-149">If the index type is **Primary XML** or **Spatial**, this column does not appear in the table.</span></span>  
  
 <span data-ttu-id="693b9-150">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="693b9-150">**Data Type**</span></span>  
 <span data-ttu-id="693b9-151">Выводит сведения о типах данных.</span><span class="sxs-lookup"><span data-stu-id="693b9-151">Displays the data type information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="693b9-152">Если столбец в таблице является вычисляемым, в поле **Тип данных** отображается "вычисляемый столбец".</span><span class="sxs-lookup"><span data-stu-id="693b9-152">If the table column is a computed column, **Data type** displays "computed column."</span></span>  
  
 <span data-ttu-id="693b9-153">**Размер**</span><span class="sxs-lookup"><span data-stu-id="693b9-153">**Size**</span></span>  
 <span data-ttu-id="693b9-154">Выводит максимальное число байтов, необходимых для хранения типа данных столбца.</span><span class="sxs-lookup"><span data-stu-id="693b9-154">Displays the maximum number of bytes required to store the column data type.</span></span> <span data-ttu-id="693b9-155">Отображает для пространственного или XML-столбца значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="693b9-155">Displays zero (0) for a spatial or XML column.</span></span>  
  
 <span data-ttu-id="693b9-156">**Удостоверение**</span><span class="sxs-lookup"><span data-stu-id="693b9-156">**Identity**</span></span>  
 <span data-ttu-id="693b9-157">Отображает, является ли столбец, принадлежащий ключу индекса, столбцом идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="693b9-157">Displays whether the column participating in the index key is an identity column.</span></span>  
  
 <span data-ttu-id="693b9-158">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="693b9-158">**Allow NULLs**</span></span>  
 <span data-ttu-id="693b9-159">Отображает, разрешено ли использование в столбце, участвующем в ключе индекса, значений NULL, которые будут записываться в таблицу или столбец представления.</span><span class="sxs-lookup"><span data-stu-id="693b9-159">Displays whether the column participating in the index key allows NULL values to be stored in the table or view column.</span></span>  
  
 <span data-ttu-id="693b9-160">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="693b9-160">**Add**</span></span>  
 <span data-ttu-id="693b9-161">Добавляет столбец к ключу индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-161">Adds a column to the index key.</span></span> <span data-ttu-id="693b9-162">Выберите столбцы таблицы в диалоговом окне **Выбор столбцов из** *\<table name>* , которое появляется при нажатии кнопки **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="693b9-162">Select table columns from the **Select Columns from** *\<table name>* dialog box that appears when you click **Add**.</span></span> <span data-ttu-id="693b9-163">После выбора одного столбца эта кнопка становится недоступной для пространственного столбца.</span><span class="sxs-lookup"><span data-stu-id="693b9-163">For a spatial index, after you select one column, this button is dimmed.</span></span>  
  
 <span data-ttu-id="693b9-164">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="693b9-164">**Remove**</span></span>  
 <span data-ttu-id="693b9-165">Удаляет выбранный столбец из ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-165">Removes the selected column from participation in the index key.</span></span>  
  
 <span data-ttu-id="693b9-166">**Вверх**</span><span class="sxs-lookup"><span data-stu-id="693b9-166">**Move Up**</span></span>  
 <span data-ttu-id="693b9-167">Перемещает выбранный столбец вверх в сетке ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-167">Moves the selected column up in the index key grid.</span></span>  
  
 <span data-ttu-id="693b9-168">**Вниз**</span><span class="sxs-lookup"><span data-stu-id="693b9-168">**Move Down**</span></span>  
 <span data-ttu-id="693b9-169">Перемещает выбранный столбец вниз в сетке ключа индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-169">Moves the selected column down in the index key grid.</span></span>  
  
 <span data-ttu-id="693b9-170">**Столбцы Columnstore**</span><span class="sxs-lookup"><span data-stu-id="693b9-170">**Columnstore columns**</span></span>  
 <span data-ttu-id="693b9-171">Нажмите кнопку **Добавить** , чтобы выбрать столбцы для индекса columnstore.</span><span class="sxs-lookup"><span data-stu-id="693b9-171">Click **Add** to select columns for the columnstore index.</span></span> <span data-ttu-id="693b9-172">Сведения об ограничениях для индекса columnstore см. в разделе [CREATE COLUMNSTORE INDEX (Transact-SQL)](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="693b9-172">For limitations on a columnstore index, see [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span></span>  
  
 <span data-ttu-id="693b9-173">**Включенные столбцы**</span><span class="sxs-lookup"><span data-stu-id="693b9-173">**Included columns**</span></span>  
 <span data-ttu-id="693b9-174">Включите неключевые столбцы в некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="693b9-174">Include nonkey columns in the nonclustered index.</span></span> <span data-ttu-id="693b9-175">Этот параметр позволяет обойти существующие в индексе ограничения на общий размер ключа индекса и максимальное число столбцов, входящих в этот ключ, за счет добавления столбцов, таких как неключевых, в конечный уровень некластеризованного индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-175">This option allows you to bypass the current index limits on the total size of an index key and the maximum number of columns participating in an index key by adding columns as nonkey columns in the leaf level of the nonclustered index.</span></span> <span data-ttu-id="693b9-176">Дополнительные сведения см. в статье [Создание индексов с включенными столбцами](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-176">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md)</span></span>  
  
##  <a name="select-index-columns-dialog-box"></a><a name="Columns"></a> <span data-ttu-id="693b9-177">Диалоговое окно «Выбор столбцов (индекса)»</span><span class="sxs-lookup"><span data-stu-id="693b9-177">Select (Index) Columns Dialog Box</span></span>  
 <span data-ttu-id="693b9-178">Используйте эту страницу для добавления столбцов на страницу **Свойства индекса — общие** при создании или изменении индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-178">Use this page to add columns to the **Index Properties General** page when creating or modifying an index.</span></span>  
  
 <span data-ttu-id="693b9-179">**Флажок**</span><span class="sxs-lookup"><span data-stu-id="693b9-179">**Check box**</span></span>  
 <span data-ttu-id="693b9-180">Выберите этот пункт, чтобы добавить столбцы.</span><span class="sxs-lookup"><span data-stu-id="693b9-180">Select to add columns.</span></span>  
  
 <span data-ttu-id="693b9-181">**имя**;</span><span class="sxs-lookup"><span data-stu-id="693b9-181">**Name**</span></span>  
 <span data-ttu-id="693b9-182">Имя столбца.</span><span class="sxs-lookup"><span data-stu-id="693b9-182">Name of the column.</span></span>  
  
 <span data-ttu-id="693b9-183">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="693b9-183">**Data Type**</span></span>  
 <span data-ttu-id="693b9-184">Тип данных столбца.</span><span class="sxs-lookup"><span data-stu-id="693b9-184">The data type of the column.</span></span>  
  
 <span data-ttu-id="693b9-185">**Байт**</span><span class="sxs-lookup"><span data-stu-id="693b9-185">**Bytes**</span></span>  
 <span data-ttu-id="693b9-186">Размер столбца в байтах.</span><span class="sxs-lookup"><span data-stu-id="693b9-186">The size of the column in bytes.</span></span>  
  
 <span data-ttu-id="693b9-187">**Удостоверение**</span><span class="sxs-lookup"><span data-stu-id="693b9-187">**Identity**</span></span>  
 <span data-ttu-id="693b9-188">Отображает **Да** для столбцов идентификаторов и **Нет** для всех остальных столбцов.</span><span class="sxs-lookup"><span data-stu-id="693b9-188">Displays **Yes** for identity columns, and **No** when the column is not an identity column.</span></span>  
  
 <span data-ttu-id="693b9-189">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="693b9-189">**Allow Nulls**</span></span>  
 <span data-ttu-id="693b9-190">Отображает **Да** , когда в определении таблицы для данного столбца разрешены значения NULL.</span><span class="sxs-lookup"><span data-stu-id="693b9-190">Displays **Yes** when the table definition allows null values for the column.</span></span> <span data-ttu-id="693b9-191">Отображает **Нет** , если в определении таблицы не разрешены значения NULL для этого столбца.</span><span class="sxs-lookup"><span data-stu-id="693b9-191">Displays **No** when the table definition does not allow nulls for the column.</span></span>  
  
##  <a name="storage-page-options"></a><a name="Storage"></a> <span data-ttu-id="693b9-192">Параметры страницы «Хранение»</span><span class="sxs-lookup"><span data-stu-id="693b9-192">Storage Page Options</span></span>  
 <span data-ttu-id="693b9-193">Эта страница позволяет просматривать и изменять свойства файловой группы или схемы секционирования для выбранного индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-193">Use this page to view or modify filegroup or partition scheme properties for the selected index.</span></span> <span data-ttu-id="693b9-194">Показывает только параметры, относящиеся к типу индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-194">Only shows options related to the type of index.</span></span>  
  
 <span data-ttu-id="693b9-195">**Файловая группа**</span><span class="sxs-lookup"><span data-stu-id="693b9-195">**Filegroup**</span></span>  
 <span data-ttu-id="693b9-196">Сохраняет индекс в указанной файловой группе.</span><span class="sxs-lookup"><span data-stu-id="693b9-196">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="693b9-197">Этот список содержит только стандартные файловые группы (ROW).</span><span class="sxs-lookup"><span data-stu-id="693b9-197">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="693b9-198">По умолчанию из этого списка выбирается первичная файловая группа (PRIMARY) текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="693b9-198">The default list selection is the PRIMARY filegroup of the database.</span></span> <span data-ttu-id="693b9-199">Дополнительные сведения см. в статье [Файлы и группы файлов базы данных](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-199">For more information, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
 <span data-ttu-id="693b9-200">**Файловая группа файлового потока**</span><span class="sxs-lookup"><span data-stu-id="693b9-200">**Filestream filegroup**</span></span>  
 <span data-ttu-id="693b9-201">Задает файловую группу для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="693b9-201">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="693b9-202">Этот список содержит только файловые группы FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="693b9-202">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="693b9-203">По умолчанию из этого списка выбирается файловая группа PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="693b9-203">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span> <span data-ttu-id="693b9-204">Дополнительные сведения см. в разделе [FILESTREAM (SQL Server)](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-204">For more information, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="693b9-205">**Схема секционирования**</span><span class="sxs-lookup"><span data-stu-id="693b9-205">**Partition scheme**</span></span>  
 <span data-ttu-id="693b9-206">Хранит индекс в схеме секционирования.</span><span class="sxs-lookup"><span data-stu-id="693b9-206">Stores the index in a partition scheme.</span></span> <span data-ttu-id="693b9-207">Если нажать кнопку **Схема секционирования** , активируется сетка внизу.</span><span class="sxs-lookup"><span data-stu-id="693b9-207">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="693b9-208">По умолчанию из списка выбирается схема секционирования, использованная для хранения данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="693b9-208">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="693b9-209">При выборе из списка другой схемы секционирования данные в сетке обновляются.</span><span class="sxs-lookup"><span data-stu-id="693b9-209">When you select a different partition scheme in the list, the information in the grid is updated.</span></span> <span data-ttu-id="693b9-210">Дополнительные сведения см. в разделе [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-210">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="693b9-211">Параметр схемы секционирования недоступен, если в базе данных нет ни одной схемы секционирования.</span><span class="sxs-lookup"><span data-stu-id="693b9-211">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="693b9-212">**Схема секционирования файлового потока**</span><span class="sxs-lookup"><span data-stu-id="693b9-212">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="693b9-213">Задает схему секционирования для данных FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="693b9-213">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="693b9-214">Схема секционирования должна быть симметрична схеме, указанной в параметре **Схема секционирования** .</span><span class="sxs-lookup"><span data-stu-id="693b9-214">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="693b9-215">Если таблица не секционирована, это поле пусто.</span><span class="sxs-lookup"><span data-stu-id="693b9-215">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="693b9-216">**Параметр схемы секционирования**</span><span class="sxs-lookup"><span data-stu-id="693b9-216">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="693b9-217">Отображает имя столбца, участвующего в схеме секционирования.</span><span class="sxs-lookup"><span data-stu-id="693b9-217">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="693b9-218">**Столбец таблицы**</span><span class="sxs-lookup"><span data-stu-id="693b9-218">**Table Column**</span></span>  
 <span data-ttu-id="693b9-219">Выберите таблицу или представление для сопоставления схеме секционирования.</span><span class="sxs-lookup"><span data-stu-id="693b9-219">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="693b9-220">**Тип данных столбца**</span><span class="sxs-lookup"><span data-stu-id="693b9-220">**Column Data Type**</span></span>  
 <span data-ttu-id="693b9-221">Выводит сведения о типах данных для данного столбца.</span><span class="sxs-lookup"><span data-stu-id="693b9-221">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="693b9-222">Если это вычисляемый столбец, в поле **Тип данных столбца** отображается отметка "вычисляемый столбец".</span><span class="sxs-lookup"><span data-stu-id="693b9-222">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="693b9-223">**Разрешить обработку в сети DML-инструкций во время переноса индекса**</span><span class="sxs-lookup"><span data-stu-id="693b9-223">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="693b9-224">Параметр дает пользователям возможность получать доступ к данным базовой таблицы или кластеризованного индекса, а также к любым связанным с ними некластеризованным индексам при операциях с индексами.</span><span class="sxs-lookup"><span data-stu-id="693b9-224">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span> <span data-ttu-id="693b9-225">Дополнительные сведения см. в статье [Выполнение операции с индексами в сети](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-225">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="693b9-226">Этот параметр недоступен для XML-индексов, а также в случае, если индекс является отключенным кластеризованным индексом.</span><span class="sxs-lookup"><span data-stu-id="693b9-226">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="693b9-227">**Укажите максимальную степень параллелизма**</span><span class="sxs-lookup"><span data-stu-id="693b9-227">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="693b9-228">Ограничивает число процессоров, используемых в одновременном исполнении планов.</span><span class="sxs-lookup"><span data-stu-id="693b9-228">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="693b9-229">При значении по умолчанию 0 используется реальное число доступных ЦП.</span><span class="sxs-lookup"><span data-stu-id="693b9-229">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="693b9-230">При установке значения 1 создание параллельных планов становится невозможным; при установке значения больше 1 ограничивается максимальное число процессоров, используемых для выполнения одного запроса.</span><span class="sxs-lookup"><span data-stu-id="693b9-230">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="693b9-231">Этот параметр становится доступным только в случае, если диалоговое окно находится в состоянии **Перестроение** или **Повторное создание** .</span><span class="sxs-lookup"><span data-stu-id="693b9-231">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span> <span data-ttu-id="693b9-232">Дополнительные сведения см. в статье [Задание параметра максимальной степени параллелизма для оптимальной производительности](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-232">For more information, see [Set the Max Degree of Parallelism Option for Optimal Performance](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="693b9-233">Если задано значение, превышающее число доступных ЦП, используется фактическое число доступных ЦП.</span><span class="sxs-lookup"><span data-stu-id="693b9-233">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="spatial-page-index-options"></a><a name="Spatial"></a> <span data-ttu-id="693b9-234">Параметры индекса (страница «Пространственный»)</span><span class="sxs-lookup"><span data-stu-id="693b9-234">Spatial Page Index Options</span></span>  
 <span data-ttu-id="693b9-235">На странице **Пространственный** можно просмотреть или задать значения пространственных свойств.</span><span class="sxs-lookup"><span data-stu-id="693b9-235">Use the **Spatial** page to view or specify the values of the spatial properties.</span></span> <span data-ttu-id="693b9-236">Дополнительные сведения см. в разделе [Пространственные данные (SQL Server)](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-236">For more information, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
### <a name="bounding-box"></a><span data-ttu-id="693b9-237">Ограничивающий прямоугольник</span><span class="sxs-lookup"><span data-stu-id="693b9-237">Bounding Box</span></span>  
 <span data-ttu-id="693b9-238">*Ограничивающий прямоугольник* представляет собой периметр сетки верхнего уровня геометрической плоскости.</span><span class="sxs-lookup"><span data-stu-id="693b9-238">The *bounding box* is the perimeter of the top-level grid of a geometric plane.</span></span> <span data-ttu-id="693b9-239">Параметры ограничивающего прямоугольника существуют только в тесселяции геометрической сетки.</span><span class="sxs-lookup"><span data-stu-id="693b9-239">The bounding-box parameters exist only in the geometry grid tessellation.</span></span> <span data-ttu-id="693b9-240">Эти параметры недоступны, если **Схемой тесселяции** является **Географическая сетка**.</span><span class="sxs-lookup"><span data-stu-id="693b9-240">These parameters are unavailable if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="693b9-241">На панели отображаются координаты ограничивающего прямоугольника **( *`X-min`* , *`Y-min`* )** и **( *`X-max`* , *`Y-max`* )** .</span><span class="sxs-lookup"><span data-stu-id="693b9-241">The panel displays the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="693b9-242">Значения координат по умолчанию отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="693b9-242">There are no default coordinate values.</span></span> <span data-ttu-id="693b9-243">Поэтому при создании нового пространственного индекса для столбца типа `geometry` необходимо указать значения координат.</span><span class="sxs-lookup"><span data-stu-id="693b9-243">Therefore, when you are creating a new spatial index on a `geometry` type column, you must specify the coordinate values.</span></span>  
  
 `X-min`  
 <span data-ttu-id="693b9-244">Координата по оси X левого нижнего угла ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="693b9-244">The X-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `Y-min`  
 <span data-ttu-id="693b9-245">Координата по оси Y левого нижнего угла ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="693b9-245">The Y-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `X-max`  
 <span data-ttu-id="693b9-246">Координата по оси X правого верхнего угла ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="693b9-246">The X-coordinate of the upper-right corner of the bounding box.</span></span>  
  
 `Y-max`  
 <span data-ttu-id="693b9-247">Координата по оси Y правого верхнего угла ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="693b9-247">The Y-coordinate of upper-right corner of the bounding box.</span></span>  
  
### <a name="general"></a><span data-ttu-id="693b9-248">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="693b9-248">General</span></span>  
 <span data-ttu-id="693b9-249">**Схема тесселяции**</span><span class="sxs-lookup"><span data-stu-id="693b9-249">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="693b9-250">Указывает схему тесселяции индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-250">Indicates the tessellation scheme of the index.</span></span> <span data-ttu-id="693b9-251">Поддерживаются следующие схемы тесселяции.</span><span class="sxs-lookup"><span data-stu-id="693b9-251">The supported tessellation schemes are as follows.</span></span>  
  
 <span data-ttu-id="693b9-252">**Геометрическая сетка**</span><span class="sxs-lookup"><span data-stu-id="693b9-252">**Geometry grid**</span></span>  
 <span data-ttu-id="693b9-253">Указывает схему тесселяции геометрической сетки, которая применяется к столбцу данных типа `geometry`.</span><span class="sxs-lookup"><span data-stu-id="693b9-253">Specifies the geometry grid tessellation scheme, which applies to a column of the `geometry` data type.</span></span>  
  
 <span data-ttu-id="693b9-254">**Автоматическая геометрическая сетка**</span><span class="sxs-lookup"><span data-stu-id="693b9-254">**Geometry Auto grid**</span></span>  
 <span data-ttu-id="693b9-255">Этот параметр включен для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , если уровень совместимости базы данных — 110 или выше.</span><span class="sxs-lookup"><span data-stu-id="693b9-255">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="693b9-256">**Географическая сетка**</span><span class="sxs-lookup"><span data-stu-id="693b9-256">**Geography grid**</span></span>  
 <span data-ttu-id="693b9-257">Указывает схему тесселяции географической сетки, которая применяется к столбцу данных типа **geography** .</span><span class="sxs-lookup"><span data-stu-id="693b9-257">Specifies the geography grid tessellation scheme, which applies to a column of the **geography** data type.</span></span>  
  
 <span data-ttu-id="693b9-258">**Автоматическая географическая сетка**</span><span class="sxs-lookup"><span data-stu-id="693b9-258">**Geography Auto grid**</span></span>  
 <span data-ttu-id="693b9-259">Этот параметр включен для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , если уровень совместимости базы данных — 110 или выше.</span><span class="sxs-lookup"><span data-stu-id="693b9-259">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="693b9-260">Сведения о реализации тесселяции в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] см. в разделе [Spatial Data (SQL Server)](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-260">For information about how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implements tessellation, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="693b9-261">**Число ячеек на объект**</span><span class="sxs-lookup"><span data-stu-id="693b9-261">**Cells Per Object**</span></span>  
 <span data-ttu-id="693b9-262">Указывает количество ячеек тесселяции, которое может использоваться для одного пространственного объекта в индексе.</span><span class="sxs-lookup"><span data-stu-id="693b9-262">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="693b9-263">Значением может быть любое целое число от 1 до 8192 включительно.</span><span class="sxs-lookup"><span data-stu-id="693b9-263">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="693b9-264">По умолчанию используется значение 16 и 8 для более ранних версий [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , когда установлен уровень совместимости базы данных 110 или больше.</span><span class="sxs-lookup"><span data-stu-id="693b9-264">The default is 16, and 8 for earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="693b9-265">Если объект на верхнем уровне охватывает больше ячеек, чем указано в параметре *n*, в ходе индексирования используется столько ячеек, сколько необходимо для полной тесселяции на верхнем уровне.</span><span class="sxs-lookup"><span data-stu-id="693b9-265">At the top level, if an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="693b9-266">В подобных случаях объекту может быть выделено больше ячеек, чем было указано.</span><span class="sxs-lookup"><span data-stu-id="693b9-266">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="693b9-267">В этом случае максимальным числом будет число ячеек, сформированных сеткой верхнего уровня, которое зависит от плотности на **уровне 1** .</span><span class="sxs-lookup"><span data-stu-id="693b9-267">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
### <a name="grids"></a><span data-ttu-id="693b9-268">Сетки</span><span class="sxs-lookup"><span data-stu-id="693b9-268">Grids</span></span>  
 <span data-ttu-id="693b9-269">Эта панель показывает плотность сетки на каждом уровне схемы тесселяции.</span><span class="sxs-lookup"><span data-stu-id="693b9-269">This panel shows the density of the grid at each level of the tessellation scheme.</span></span> <span data-ttu-id="693b9-270">Плотность указывается как **низкая**, **средняя**или **высокая**.</span><span class="sxs-lookup"><span data-stu-id="693b9-270">Density is specified as **Low**, **Medium**, or **High**.</span></span> <span data-ttu-id="693b9-271">Значение по умолчанию — **средняя**.</span><span class="sxs-lookup"><span data-stu-id="693b9-271">The default is **Medium**.</span></span> <span data-ttu-id="693b9-272">**Низкая** представляет сетку 4x4 (16 ячеек), **средняя** представляет сетку 8x8 (64 ячейки), и **высокая** представляет сетку 16x16 (256 ячеек).</span><span class="sxs-lookup"><span data-stu-id="693b9-272">**Low** represents a 4x4 grid (16 cells), **Medium** represents an 8x8 grid (64 cells), and **High** represents a 16x16 grid (256 cells).</span></span> <span data-ttu-id="693b9-273">Эти параметры недоступны, если выбраны параметры тесселяции **Автоматическая геометрическая сетка** или **Автоматическая географическая сетка** .</span><span class="sxs-lookup"><span data-stu-id="693b9-273">These options are not available when the **Geometry Auto grid** or **Geography Auto grid** tessellation options are chosen.</span></span>  
  
 <span data-ttu-id="693b9-274">**Уровень 1**</span><span class="sxs-lookup"><span data-stu-id="693b9-274">**Level 1**</span></span>  
 <span data-ttu-id="693b9-275">Плотность сетки на первом (верхнем) уровне.</span><span class="sxs-lookup"><span data-stu-id="693b9-275">The density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="693b9-276">**Уровень 2**</span><span class="sxs-lookup"><span data-stu-id="693b9-276">**Level 2**</span></span>  
 <span data-ttu-id="693b9-277">Плотность сетки на втором уровне.</span><span class="sxs-lookup"><span data-stu-id="693b9-277">The density of the second-level grid.</span></span>  
  
 <span data-ttu-id="693b9-278">**Уровень 3**</span><span class="sxs-lookup"><span data-stu-id="693b9-278">**Level 3**</span></span>  
 <span data-ttu-id="693b9-279">Плотность сетки на третьем уровне.</span><span class="sxs-lookup"><span data-stu-id="693b9-279">The density of the third-level grid.</span></span>  
  
 <span data-ttu-id="693b9-280">**Уровень 4**</span><span class="sxs-lookup"><span data-stu-id="693b9-280">**Level 4**</span></span>  
 <span data-ttu-id="693b9-281">Плотность сетки на четвертом уровне.</span><span class="sxs-lookup"><span data-stu-id="693b9-281">The density of the fourth-level grid.</span></span>  
  
##  <a name="filter-page"></a><a name="Filter"></a> <span data-ttu-id="693b9-282">Страница «Фильтр»</span><span class="sxs-lookup"><span data-stu-id="693b9-282">Filter Page</span></span>  
 <span data-ttu-id="693b9-283">Эта страница позволяет ввести предикат фильтра для отфильтрованного индекса.</span><span class="sxs-lookup"><span data-stu-id="693b9-283">Use this page to enter the filter predicate for a filtered index.</span></span> <span data-ttu-id="693b9-284">Дополнительные сведения см. в разделе [Create Filtered Indexes](create-filtered-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="693b9-284">For more information, see [Create Filtered Indexes](create-filtered-indexes.md).</span></span>  
  
 <span data-ttu-id="693b9-285">**Критерий фильтра**</span><span class="sxs-lookup"><span data-stu-id="693b9-285">**Filter Expression**</span></span>  
 <span data-ttu-id="693b9-286">Определяет столбцы данных, которые будут включены в фильтруемый индекс.</span><span class="sxs-lookup"><span data-stu-id="693b9-286">Defines which data rows to include in the filtered index.</span></span> <span data-ttu-id="693b9-287">Например `StartDate > '20000101' AND EndDate IS NOT NULL'.`.</span><span class="sxs-lookup"><span data-stu-id="693b9-287">For example, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="693b9-288">См. также:</span><span class="sxs-lookup"><span data-stu-id="693b9-288">See Also</span></span>  
 <span data-ttu-id="693b9-289">[Установка параметров индекса](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="693b9-289">[Set Index Options](set-index-options.md) </span></span>  
 <span data-ttu-id="693b9-290">[INDEXPROPERTY (Transact-SQL)](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="693b9-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 [<span data-ttu-id="693b9-291">sys.indexes (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="693b9-291">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
