---
title: Диалоговое окно "Пространственные индексы" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.spatialindexes
ms.assetid: 4d84239a-68c7-4aa2-8602-2b51dd07260f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e401b7f93a8376b1c6dc0c75ca29cbdc8a39863d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659068"
---
# <a name="spatial-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="b30ff-102">Диалоговое окно «Пространственные индексы» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b30ff-102">Spatial Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="b30ff-103">Используйте диалоговое окно **Пространственные индексы** для создания индексов для столбцов с типом данных **geometry** или **geography** (*пространственный столбец*), которые не могут быть индексированы с использованием диалогового окна **Индексы/Ключи** .</span><span class="sxs-lookup"><span data-stu-id="b30ff-103">Use the **Spatial Indexes** dialog box to create indexes for columns of the **geometry** or **geography** data type (*spatial columns*), which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="b30ff-104">Для каждого пространственного столбца может существовать несколько пространственных индексов, но их следует создавать по очереди.</span><span class="sxs-lookup"><span data-stu-id="b30ff-104">Each spatial column can have more than one spatial index, but they must be created one at a time.</span></span>  
  
 <span data-ttu-id="b30ff-105">Сведения об ограничениях, накладываемых на создание пространственных индексов, см. в разделе [Общие сведения о пространственных индексах](../../relational-databases/spatial/spatial-indexes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b30ff-105">For information about restrictions on spatial index creation, see [Spatial Indexes Overview](../../relational-databases/spatial/spatial-indexes-overview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b30ff-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b30ff-106">Options</span></span>  
 <span data-ttu-id="b30ff-107">**Выбранный пространственный индекс**</span><span class="sxs-lookup"><span data-stu-id="b30ff-107">**Selected Spatial Index**</span></span>  
 <span data-ttu-id="b30ff-108">Отображает список существующих пространственных индексов.</span><span class="sxs-lookup"><span data-stu-id="b30ff-108">Lists existing spatial indexes.</span></span> <span data-ttu-id="b30ff-109">Выберите индекс для просмотра его свойств.</span><span class="sxs-lookup"><span data-stu-id="b30ff-109">Select an index to show its properties.</span></span> <span data-ttu-id="b30ff-110">Если этот список пуст, то для этой таблицы не было определено ни одного пространственного индекса.</span><span class="sxs-lookup"><span data-stu-id="b30ff-110">If the list is empty, no spatial indexes have been defined for the table.</span></span>  
  
 <span data-ttu-id="b30ff-111">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="b30ff-111">**Add**</span></span>  
 <span data-ttu-id="b30ff-112">Создает новый пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="b30ff-112">Creates a new spatial index.</span></span>  
  
 <span data-ttu-id="b30ff-113">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="b30ff-113">**Delete**</span></span>  
 <span data-ttu-id="b30ff-114">Удаляет пространственный индекс, выбранный в списке **Выбранный пространственный индекс** .</span><span class="sxs-lookup"><span data-stu-id="b30ff-114">Deletes the spatial index selected in the **Selected Spatial Index** list.</span></span>  
  
 <span data-ttu-id="b30ff-115">**Число ячеек на объект**</span><span class="sxs-lookup"><span data-stu-id="b30ff-115">**Cells Per Object**</span></span>  
 <span data-ttu-id="b30ff-116">Указывает количество ячеек тесселяции, которое может использоваться для одного пространственного объекта в индексе.</span><span class="sxs-lookup"><span data-stu-id="b30ff-116">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="b30ff-117">Значением может быть любое целое число от 1 до 8192 включительно.</span><span class="sxs-lookup"><span data-stu-id="b30ff-117">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="b30ff-118">Значение по умолчанию равно 16.</span><span class="sxs-lookup"><span data-stu-id="b30ff-118">The default is 16.</span></span>  
  
 <span data-ttu-id="b30ff-119">Если объект охватывает больше ячеек, чем указано в параметре *n*, в ходе индексирования используется столько ячеек, сколько необходимо для полной тесселяции на верхнем уровне.</span><span class="sxs-lookup"><span data-stu-id="b30ff-119">If an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="b30ff-120">В подобных случаях объекту может быть выделено больше ячеек, чем было указано.</span><span class="sxs-lookup"><span data-stu-id="b30ff-120">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="b30ff-121">В этом случае максимальным числом будет число ячеек, сформированных сеткой верхнего уровня, которое зависит от плотности на **уровне 1** .</span><span class="sxs-lookup"><span data-stu-id="b30ff-121">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
 <span data-ttu-id="b30ff-122">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="b30ff-122">**Columns**</span></span>  
 <span data-ttu-id="b30ff-123">Указывает имя столбца и порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="b30ff-123">Indicates the column name and sort order.</span></span>  
  
 <span data-ttu-id="b30ff-124">**IsSpatialIndex**</span><span class="sxs-lookup"><span data-stu-id="b30ff-124">**IsSpatialIndex**</span></span>  
 <span data-ttu-id="b30ff-125">Указывает, что выбран пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="b30ff-125">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="b30ff-126">**Уровень 1**</span><span class="sxs-lookup"><span data-stu-id="b30ff-126">**Level 1**</span></span>  
 <span data-ttu-id="b30ff-127">Указывает плотность сетки на первом (верхнем) уровне.</span><span class="sxs-lookup"><span data-stu-id="b30ff-127">Indicates the density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="b30ff-128">**Уровень 2**</span><span class="sxs-lookup"><span data-stu-id="b30ff-128">**Level 2**</span></span>  
 <span data-ttu-id="b30ff-129">Указывает плотность сетки на втором уровне.</span><span class="sxs-lookup"><span data-stu-id="b30ff-129">Indicates the density of the second-level grid.</span></span>  
  
 <span data-ttu-id="b30ff-130">**Уровень 3**</span><span class="sxs-lookup"><span data-stu-id="b30ff-130">**Level 3**</span></span>  
 <span data-ttu-id="b30ff-131">Указывает плотность сетки на третьем уровне.</span><span class="sxs-lookup"><span data-stu-id="b30ff-131">Indicates the density of the third-level grid.</span></span>  
  
 <span data-ttu-id="b30ff-132">**Уровень 4**</span><span class="sxs-lookup"><span data-stu-id="b30ff-132">**Level 4**</span></span>  
 <span data-ttu-id="b30ff-133">Указывает плотность сетки на четвертом уровне.</span><span class="sxs-lookup"><span data-stu-id="b30ff-133">Indicates the density of the fourth-level grid.</span></span>  
  
 <span data-ttu-id="b30ff-134">**Схема тесселяции**</span><span class="sxs-lookup"><span data-stu-id="b30ff-134">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="b30ff-135">Указывает схему тесселяции.</span><span class="sxs-lookup"><span data-stu-id="b30ff-135">Indicates the tessellation scheme:</span></span>  
  
 <span data-ttu-id="b30ff-136">Параметры столбцов типа**Geometry** :</span><span class="sxs-lookup"><span data-stu-id="b30ff-136">**Geometry** column options:</span></span>  
  
-   <span data-ttu-id="b30ff-137">**Геометрическая сетка** для геометрического столбца</span><span class="sxs-lookup"><span data-stu-id="b30ff-137">**Geometry grid** for a geometry column</span></span>  
  
-   <span data-ttu-id="b30ff-138">**Географическая сетка** для географического столбца</span><span class="sxs-lookup"><span data-stu-id="b30ff-138">**Geography grid** for a geography column</span></span>  
  
 <span data-ttu-id="b30ff-139">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b30ff-139">**Type**</span></span>  
 <span data-ttu-id="b30ff-140">Указывает, что выбран пространственный индекс.</span><span class="sxs-lookup"><span data-stu-id="b30ff-140">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="b30ff-141">**X-макс**</span><span class="sxs-lookup"><span data-stu-id="b30ff-141">**X-max**</span></span>  
 <span data-ttu-id="b30ff-142">Задает координату x правого верхнего угла ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b30ff-142">Specifies the x-coordinate of the upper-right corner of the bounding box.</span></span> <span data-ttu-id="b30ff-143">Это свойство будет недоступно, если параметр **Схема тесселяции** имеет значение **Географическая сетка**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-143">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="b30ff-144">**X-мин**</span><span class="sxs-lookup"><span data-stu-id="b30ff-144">**X-min**</span></span>  
 <span data-ttu-id="b30ff-145">Задает координату левого нижнего угла ограничивающего прямоугольника по оси X.</span><span class="sxs-lookup"><span data-stu-id="b30ff-145">Specifies the x-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="b30ff-146">Это свойство будет недоступно, если параметр **Схема тесселяции** имеет значение **Географическая сетка**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-146">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="b30ff-147">**Y-макс**</span><span class="sxs-lookup"><span data-stu-id="b30ff-147">**Y-max**</span></span>  
 <span data-ttu-id="b30ff-148">Задает координату правого верхнего угла ограничивающего прямоугольника по оси Y.</span><span class="sxs-lookup"><span data-stu-id="b30ff-148">Specifies the y-coordinate of upper-right corner of the bounding box.</span></span> <span data-ttu-id="b30ff-149">Это свойство будет недоступно, если параметр **Схема тесселяции** имеет значение **Географическая сетка**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-149">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="b30ff-150">**Y-мин**</span><span class="sxs-lookup"><span data-stu-id="b30ff-150">**Y-min**</span></span>  
 <span data-ttu-id="b30ff-151">Задает координату левого нижнего угла ограничивающего прямоугольника по оси Y.</span><span class="sxs-lookup"><span data-stu-id="b30ff-151">Specifies the y-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="b30ff-152">Это свойство будет недоступно, если параметр **Схема тесселяции** имеет значение **Географическая сетка**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-152">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="b30ff-153">**Удостоверение**</span><span class="sxs-lookup"><span data-stu-id="b30ff-153">**Identity**</span></span>  
 <span data-ttu-id="b30ff-154">При развертывании показывает поля свойств **Имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="b30ff-154">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="b30ff-155">**(Имя)**</span><span class="sxs-lookup"><span data-stu-id="b30ff-155">**(Name)**</span></span>  
 <span data-ttu-id="b30ff-156">Отображает имя пространственного индекса.</span><span class="sxs-lookup"><span data-stu-id="b30ff-156">Shows the name of the spatial index.</span></span> <span data-ttu-id="b30ff-157">Если создается новый индекс, ему присваивается имя по умолчанию, в зависимости от таблицы, отображаемой в активном окне конструктора таблиц.</span><span class="sxs-lookup"><span data-stu-id="b30ff-157">When a new index is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="b30ff-158">Имя можно изменить в любой момент.</span><span class="sxs-lookup"><span data-stu-id="b30ff-158">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="b30ff-159">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b30ff-159">**Description**</span></span>  
 <span data-ttu-id="b30ff-160">Описывает индекс.</span><span class="sxs-lookup"><span data-stu-id="b30ff-160">Describes the index.</span></span> <span data-ttu-id="b30ff-161">Чтобы ввести более подробное описание, нажмите кнопку **Описание**, а затем — кнопку с многоточием ( **...** ) справа от поля свойства.</span><span class="sxs-lookup"><span data-stu-id="b30ff-161">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="b30ff-162">При этом появится большее поле для записи текста.</span><span class="sxs-lookup"><span data-stu-id="b30ff-162">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="b30ff-163">**Категория конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="b30ff-163">**Table Designer Category**</span></span>  
 <span data-ttu-id="b30ff-164">Когда она открыта, показывает сведения о свойствах данного пространственного индекса.</span><span class="sxs-lookup"><span data-stu-id="b30ff-164">When expanded, shows information about the properties of this spatial index.</span></span>  
  
 <span data-ttu-id="b30ff-165">**Характеристики заполнения**</span><span class="sxs-lookup"><span data-stu-id="b30ff-165">**Fill Specification**</span></span>  
 <span data-ttu-id="b30ff-166">В развернутом состоянии отображает сведения о параметрах **Коэффициент заполнения** и **Разредить индекс**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-166">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="b30ff-167">**Коэффициент заполнения**</span><span class="sxs-lookup"><span data-stu-id="b30ff-167">**Fill Factor**</span></span>  
 <span data-ttu-id="b30ff-168">Укажите, какой процент индексной страницы может заполнить система.</span><span class="sxs-lookup"><span data-stu-id="b30ff-168">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="b30ff-169">Когда страница заполнена, при добавлении новых данных система должна разбить страницу, что снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="b30ff-169">When a page is full, if new data is added, the system must split the page, which impairs performance.</span></span>  
  
-   <span data-ttu-id="b30ff-170">Значение, равное 100, означает, что страница будет заполнена; в этом случае требуется меньше всего объема пространства для хранения, но также будет наименее эффективно.</span><span class="sxs-lookup"><span data-stu-id="b30ff-170">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="b30ff-171">Данное значение должно использоваться только в том случае, если данные не будут изменяться: например в таблице, предназначенной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b30ff-171">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="b30ff-172">Меньшее значение оставляет больше пустого пространства на страницах данных, что снижает необходимость разбиения страницы данных с ростом индексов.</span><span class="sxs-lookup"><span data-stu-id="b30ff-172">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="b30ff-173">Однако это потребует больше пространства для хранения.</span><span class="sxs-lookup"><span data-stu-id="b30ff-173">However, it requires more storage space.</span></span> <span data-ttu-id="b30ff-174">Этот параметр более необходим в случае, если данные в таблице будут меняться.</span><span class="sxs-lookup"><span data-stu-id="b30ff-174">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="b30ff-175">**Разредить индекс**</span><span class="sxs-lookup"><span data-stu-id="b30ff-175">**Pad Index**</span></span>  
 <span data-ttu-id="b30ff-176">Устанавливает для страниц в данном индексе такой же процент пустого пространства (заполнения), который указан в поле **Коэффициент заполнения**.</span><span class="sxs-lookup"><span data-stu-id="b30ff-176">Provides pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="b30ff-177">**Разрешить блокировку страниц**</span><span class="sxs-lookup"><span data-stu-id="b30ff-177">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="b30ff-178">Указывает, разрешить или запретить блокировку на уровне страниц для данного индекса.</span><span class="sxs-lookup"><span data-stu-id="b30ff-178">Specifies whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="b30ff-179">Разрешение или запрещение блокировок на уровне страниц влияет на производительность базы данных.</span><span class="sxs-lookup"><span data-stu-id="b30ff-179">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="b30ff-180">**Повторное вычисление статистики**</span><span class="sxs-lookup"><span data-stu-id="b30ff-180">**Re-compute  Statistics**</span></span>  
 <span data-ttu-id="b30ff-181">Указывает, нужно ли рассчитывать статистику заново при создании индекса.</span><span class="sxs-lookup"><span data-stu-id="b30ff-181">Specifies whether to compute new statistics when the index is created.</span></span> <span data-ttu-id="b30ff-182">Повторное вычисление статистики замедляет построение индексов, но обычно улучшает производительность запросов.</span><span class="sxs-lookup"><span data-stu-id="b30ff-182">Recomputing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="b30ff-183">**Разрешить блокировку строк**</span><span class="sxs-lookup"><span data-stu-id="b30ff-183">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="b30ff-184">Указывает, разрешить или запретить блокировку на уровне строк для данного индекса.</span><span class="sxs-lookup"><span data-stu-id="b30ff-184">Specifies whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="b30ff-185">Разрешение или запрещение блокировок на уровне строк влияет на производительность базы данных.</span><span class="sxs-lookup"><span data-stu-id="b30ff-185">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30ff-186">См. также:</span><span class="sxs-lookup"><span data-stu-id="b30ff-186">See Also</span></span>  
 [<span data-ttu-id="b30ff-187">Общие сведения о пространственных индексах</span><span class="sxs-lookup"><span data-stu-id="b30ff-187">Spatial Indexes Overview</span></span>](../../relational-databases/spatial/spatial-indexes-overview.md)  
  
  
