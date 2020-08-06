---
title: Изменение измерения даты | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4689d780-4bf6-4cf8-8fde-eb3f15dd668a
author: minewiskan
ms.author: owend
ms.openlocfilehash: b4978e9fe3acd93ddfdca707d2c2353bf171ba12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665654"
---
# <a name="modifying-the-date-dimension"></a><span data-ttu-id="a7db0-102">Изменение измерения Date</span><span class="sxs-lookup"><span data-stu-id="a7db0-102">Modifying the Date Dimension</span></span>
  <span data-ttu-id="a7db0-103">В ходе выполнения задач этого раздела мы создадим определяемую пользователем иерархию и изменим имена элементов, отображаемых для атрибутов «Дата», «Месяц», «Календарный квартал» и «Календарное полугодие».</span><span class="sxs-lookup"><span data-stu-id="a7db0-103">In the tasks in this topic, you create a user-defined hierarchy and change the member names that are displayed for the Date, Month, Calendar Quarter, and Calendar Semester attributes.</span></span> <span data-ttu-id="a7db0-104">Также мы определим составные ключи для атрибутов, настроим порядок сортировки элементов измерения и зададим связи атрибутов.</span><span class="sxs-lookup"><span data-stu-id="a7db0-104">You also define composite keys for attributes, control the sort order of dimension members, and define attribute relationships.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="a7db0-105">Добавление именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="a7db0-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="a7db0-106">К таблице в представлении источника данных можно добавить именованное вычисление, которое является выражением SQL и представляет собой вычисляемый столбец,</span><span class="sxs-lookup"><span data-stu-id="a7db0-106">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="a7db0-107">Это выражение имеет вид и функции столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="a7db0-107">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="a7db0-108">Именованные вычисления позволяют расширять реляционную схему таблиц, существующих в представлении источника данных, не изменяя таблицы в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="a7db0-108">Named calculations enable you to extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="a7db0-109">Дополнительные сведения см. в разделе [Определение именованных вычислений в представлении источника данных (службы Analysis Services)](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="a7db0-109">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="a7db0-110">Добавление именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="a7db0-110">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="a7db0-111">Чтобы открыть представление источника данных **Adventure Works DW 2012** , дважды щелкните его в папке **Представления источников данных** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="a7db0-111">To open the **Adventure Works DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="a7db0-112">В нижней части панели **таблицы** щелкните правой кнопкой мыши `Date` и выберите команду **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-112">Near the bottom of the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="a7db0-113">В диалоговом окне **Создание именованного вычисления** введите `SimpleDate` в поле **имя столбца** , а затем в поле Выражение введите или скопируйте и вставьте следующую `DATENAME` инструкцию **Expression** :</span><span class="sxs-lookup"><span data-stu-id="a7db0-113">In the **Create Named Calculation** dialog box, type `SimpleDate` in the **Column name** box, and then type or copy and paste the following `DATENAME` statement in the **Expression** box:</span></span>  
  
    ```  
    DATENAME(mm, FullDateAlternateKey) + ' ' +  
    DATENAME(dd, FullDateAlternateKey) + ', ' +  
    DATENAME(yy, FullDateAlternateKey)  
    ```  
  
     <span data-ttu-id="a7db0-114">Инструкция `DATENAME` извлекает из столбца FullDateAlternateKey значения числа, месяца и года.</span><span class="sxs-lookup"><span data-stu-id="a7db0-114">The `DATENAME` statement extracts the year, month, and day values from the FullDateAlternateKey column.</span></span> <span data-ttu-id="a7db0-115">Этот новый столбец будет содержать отображаемое имя для атрибута FullDateAlternateKey.</span><span class="sxs-lookup"><span data-stu-id="a7db0-115">You will use this new column as the displayed name for the FullDateAlternateKey attribute.</span></span>  
  
4.  <span data-ttu-id="a7db0-116">Нажмите кнопку **ОК**, а затем разверните узел `Date` на панели **таблицы** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-116">Click **OK**, and then expand `Date` in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="a7db0-117">`SimpleDate`Именованное вычисление отображается в списке столбцов в таблице Date со значком, указывающим на то, что это именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="a7db0-117">The `SimpleDate` named calculation appears in the list of columns in the Date table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="a7db0-118">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-118">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="a7db0-119">На панели **таблицы** щелкните правой кнопкой мыши `Date` и выберите **Просмотр данных**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-119">In the **Tables** pane, right-click `Date`, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="a7db0-120">Прокрутите вправо и просмотрите последний столбец в представлении **Просмотр таблицы "Дата"** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-120">Scroll to the right to review the last column in the **Explore Date Table** view.</span></span>  
  
     <span data-ttu-id="a7db0-121">Обратите внимание, что `SimpleDate` столбец отображается в представлении источника данных и правильно объединяет данные из нескольких столбцов из базового источника данных, не изменяя исходный источник данных.</span><span class="sxs-lookup"><span data-stu-id="a7db0-121">Notice that the `SimpleDate` column appears in the data source view, correctly concatenating data from several columns from the underlying data source, without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="a7db0-122">Закройте представление **Просмотр таблицы "Дата"** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-122">Close the **Explore Date Table** view.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="a7db0-123">Использование именованных вычислений в качестве имен элементов</span><span class="sxs-lookup"><span data-stu-id="a7db0-123">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="a7db0-124">После создания именованного вычисления в представлении источника данных это вычисление можно использовать в качестве свойства атрибута.</span><span class="sxs-lookup"><span data-stu-id="a7db0-124">After you create a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="a7db0-125">Использование именованного вычисления в качестве имен элементов</span><span class="sxs-lookup"><span data-stu-id="a7db0-125">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="a7db0-126">Откройте измерение Date в **конструкторе измерений** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7db0-126">Open **Dimension Designer** for the Date dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a7db0-127">Для этого дважды щелкните `Date` измерение в узле **измерения** **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-127">To do this, double-click the `Date` dimension in the **Dimensions** node of **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="a7db0-128">На панели **Атрибуты** на вкладке **Структура измерения** выберите атрибут **Date Key** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-128">In the **Attributes** pane of the **Dimension Structure** tab, click the **Date Key** attribute.</span></span>  
  
3.  <span data-ttu-id="a7db0-129">Если окно "Свойства" не открыто, откройте его и нажмите в строке заголовка кнопку **Автоматически скрывать** , чтобы оно оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="a7db0-129">If the Properties window is not open, open the Properties window, and then click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="a7db0-130">Щелкните поле свойства **NameColumn** в нижней части окна, а затем нажмите кнопку обзора (**...**), чтобы открыть диалоговое окно **Столбец имени** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-130">Click the **NameColumn** property field near the bottom of the window, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
5.  <span data-ttu-id="a7db0-131">Выберите `SimpleDate` в нижней части списка **Исходный столбец** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-131">Select `SimpleDate` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="a7db0-132">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-132">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="a7db0-133">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="a7db0-133">Creating a Hierarchy</span></span>  
 <span data-ttu-id="a7db0-134">Иерархию можно создать, перетащив атрибут с панели **Атрибуты** на панель **Иерархии** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-134">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="a7db0-135">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="a7db0-135">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="a7db0-136">На вкладке **Структура измерения** конструктора измерений для `Date` измерения перетащите атрибут **календарный год** с панели **атрибуты** на панель **иерархии** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-136">In **Dimension Structure** tab of the Dimension Designer for the `Date` dimension, drag the **Calendar Year** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="a7db0-137">Перетащите атрибут **Календарное полугодие** с панели **Атрибуты** в ячейку **\<new level>** на панели **Иерархии** под уровнем **Календарный год** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-137">Drag the **Calendar Semester** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Year** level.</span></span>  
  
3.  <span data-ttu-id="a7db0-138">Перетащите атрибут **Календарный квартал** с панели **Атрибуты** в ячейку **\<new level>** на панели **Иерархии** под уровнем **Календарное полугодие** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-138">Drag the **Calendar Quarter** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Semester** level.</span></span>  
  
4.  <span data-ttu-id="a7db0-139">Перетащите атрибут **English Month Name** с панели **Атрибуты** в ячейку **\<new level>** на панели **Иерархии** под уровнем **Календарный квартал** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-139">Drag the **English Month Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Quarter** level.</span></span>  
  
5.  <span data-ttu-id="a7db0-140">Перетащите атрибут **Date Key** с панели **Атрибуты** в ячейку **\<new level>** на панели **Иерархии** под уровнем **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-140">Drag the **Date Key** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **English Month Name** level.</span></span>  
  
6.  <span data-ttu-id="a7db0-141">На панели **иерархии** щелкните правой кнопкой мыши строку заголовка иерархии **Иерархия** , выберите команду **Переименовать**, а затем введите `Calendar Date` .</span><span class="sxs-lookup"><span data-stu-id="a7db0-141">In the **Hierarchies** pane, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Calendar Date`.</span></span>  
  
7.  <span data-ttu-id="a7db0-142">При щелчке правой кнопкой мыши контекстного меню в `Calendar Date` иерархии переименуйте уровень **английское название месяца** на `Calendar Month` , а затем переименуйте уровень **ключа даты** в `Date` .</span><span class="sxs-lookup"><span data-stu-id="a7db0-142">By using the right-click context menu, in the `Calendar Date` hierarchy, rename the **English Month Name** level to `Calendar Month`, and then rename the **Date Key** level to `Date`.</span></span>  
  
8.  <span data-ttu-id="a7db0-143">Удалите атрибут **Full Date Alternate Key** на панели **Атрибуты** , так как он больше не понадобится.</span><span class="sxs-lookup"><span data-stu-id="a7db0-143">Delete the **Full Date Alternate Key** attribute from the **Attributes** pane because you will not be using it.</span></span> <span data-ttu-id="a7db0-144">Нажмите кнопку **OK** в окне подтверждения **Удалить объекты** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-144">Click **OK** in the **Delete Objects** confirmation window.</span></span>  
  
9. <span data-ttu-id="a7db0-145">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-145">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="a7db0-146">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="a7db0-146">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="a7db0-147">Необходимо определять связи между атрибутами, если базовые данные это поддерживают.</span><span class="sxs-lookup"><span data-stu-id="a7db0-147">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="a7db0-148">Определение связей между атрибутами ускоряет обработку измерений, секций и запросов.</span><span class="sxs-lookup"><span data-stu-id="a7db0-148">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="a7db0-149">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="a7db0-149">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="a7db0-150">В **конструкторе измерений** для `Date` измерения перейдите на вкладку **связи атрибутов** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-150">In the **Dimension Designer** for the `Date` dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="a7db0-151">На диаграмме щелкните правой кнопкой мыши атрибут **English Month Name** и выберите команду **Создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-151">In the diagram, right-click the **English Month Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="a7db0-152">В диалоговом окне **Создание связи атрибутов** свойство **Исходный атрибут** имеет значение **English Month Name**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-152">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **English Month Name**.</span></span> <span data-ttu-id="a7db0-153">Задайте для поля **Связанный атрибут** значение **Календарный квартал**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-153">Set the **Related Attribute** to **Calendar Quarter**.</span></span>  
  
4.  <span data-ttu-id="a7db0-154">В списке **Тип связи** выберите тип **Жесткая**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-154">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="a7db0-155">Связь имеет тип **Жесткая** , так как связи между элементами не будут меняться с течением времени.</span><span class="sxs-lookup"><span data-stu-id="a7db0-155">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span>  
  
5.  <span data-ttu-id="a7db0-156">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-156">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="a7db0-157">На диаграмме щелкните правой кнопкой мыши атрибут **Календарный квартал** и выберите команду **Создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-157">In the diagram, right-click the **Calendar Quarter** attribute, and then click **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="a7db0-158">В диалоговом окне **Создание связи атрибутов** поле **Исходный атрибут** имеет значение **Calendar Quarter**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-158">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Quarter**.</span></span> <span data-ttu-id="a7db0-159">Задайте для поля **Связанный атрибут** значение **Календарное полугодие**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-159">Set the **Related Attribute** to **Calendar Semester**.</span></span>  
  
8.  <span data-ttu-id="a7db0-160">В списке **Тип связи** выберите тип **Жесткая**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-160">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="a7db0-161">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-161">Click **OK**.</span></span>  
  
10. <span data-ttu-id="a7db0-162">На диаграмме щелкните правой кнопкой мыши атрибут **Календарное полугодие** , а затем выберите команду **Создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-162">In the diagram, right-click the **Calendar Semester** attribute, and then click **New Attribute Relationship**.</span></span>  
  
11. <span data-ttu-id="a7db0-163">В диалоговом окне **Создание связи атрибутов** поле **Исходный атрибут** имеет значение **Календарное полугодие**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-163">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Semester**.</span></span> <span data-ttu-id="a7db0-164">Задайте для поля **Связанный атрибут** значение **Календарный год**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-164">Set the **Related Attribute** to **Calendar Year**.</span></span>  
  
12. <span data-ttu-id="a7db0-165">В списке **Тип связи** выберите тип **Жесткая**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-165">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
13. <span data-ttu-id="a7db0-166">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-166">Click **OK**.</span></span>  
  
14. <span data-ttu-id="a7db0-167">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-167">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="providing-unique-dimension-member-names"></a><span data-ttu-id="a7db0-168">Создание уникальных имен для элементов измерения</span><span class="sxs-lookup"><span data-stu-id="a7db0-168">Providing Unique Dimension Member Names</span></span>  
 <span data-ttu-id="a7db0-169">В этой задаче будут созданы столбцы понятных имен, которые будут использоваться для атрибутов **EnglishMonthName**, **CalendarQuarter**и **CalendarSemester** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-169">In this task, you will create user-friendly name columns that will be used by the **EnglishMonthName**, **CalendarQuarter**, and **CalendarSemester** attributes.</span></span>  
  
#### <a name="to-provide-unique-dimension-member-names"></a><span data-ttu-id="a7db0-170">Создание уникальных имен для элементов измерения</span><span class="sxs-lookup"><span data-stu-id="a7db0-170">To provide unique dimension member names</span></span>  
  
1.  <span data-ttu-id="a7db0-171">Чтобы переключиться на представление источника данных \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* , дважды щелкните его в папке **представления источников данных** в Обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="a7db0-171">To switch to the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="a7db0-172">На панели **таблицы** щелкните правой кнопкой мыши `Date` и выберите команду **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-172">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="a7db0-173">В диалоговом окне **Создание именованного вычисления** введите `MonthName` в поле **имя столбца** , а затем в поле **выражение** введите или скопируйте и вставьте следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="a7db0-173">In the **Create Named Calculation** dialog box, type `MonthName` in the **Column name** box, and then type or copy and paste the following statement in the **Expression** box:</span></span>  
  
    ```  
    EnglishMonthName+' '+ CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="a7db0-174">Эта инструкция объединяет месяц и год для каждого месяца в таблице в новый столбец.</span><span class="sxs-lookup"><span data-stu-id="a7db0-174">The statement concatenates the month and year for each month in the table into a new column.</span></span>  
  
4.  <span data-ttu-id="a7db0-175">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-175">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a7db0-176">На панели **таблицы** щелкните правой кнопкой мыши `Date` и выберите команду **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-176">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="a7db0-177">В диалоговом окне **Создание именованного вычисления** введите `CalendarQuarterDesc` в поле **имя столбца** , а затем в поле **выражение** введите или скопируйте и вставьте следующий скрипт SQL:</span><span class="sxs-lookup"><span data-stu-id="a7db0-177">In the **Create Named Calculation** dialog box, type `CalendarQuarterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    'Q' + CONVERT(CHAR (1), CalendarQuarter) +' '+ 'CY ' +  
    CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="a7db0-178">Этот скрипт SQL помещает в новый столбец объединение календарного квартала и года для каждого квартала в таблице.</span><span class="sxs-lookup"><span data-stu-id="a7db0-178">This SQL script concatenates the calendar quarter and year for each quarter in the table into a new column.</span></span>  
  
7.  <span data-ttu-id="a7db0-179">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-179">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="a7db0-180">На панели **таблицы** щелкните правой кнопкой мыши `Date` и выберите команду **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-180">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
9. <span data-ttu-id="a7db0-181">В диалоговом окне **Создание именованного вычисления** введите `CalendarSemesterDesc` в поле **имя столбца** , а затем в поле **выражение** введите или скопируйте и вставьте следующий скрипт SQL:</span><span class="sxs-lookup"><span data-stu-id="a7db0-181">In the **Create Named Calculation** dialog box, type `CalendarSemesterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    CASE  
    WHEN CalendarSemester = 1 THEN 'H1' + ' ' + 'CY' + ' '   
           + CONVERT(CHAR(4), CalendarYear)  
    ELSE  
    'H2' + ' ' + 'CY' + ' ' + CONVERT(CHAR(4), CalendarYear)  
    END  
    ```  
  
     <span data-ttu-id="a7db0-182">Этот скрипт SQL помещает в новый столбец объединение календарного полугодия и года для каждого полугодия в таблице.</span><span class="sxs-lookup"><span data-stu-id="a7db0-182">This SQL script concatenates the calendar semester and year for each semester in the table into a new column.</span></span>  
  
10. <span data-ttu-id="a7db0-183">Нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="a7db0-183">Click **OK.**</span></span>  
  
11. <span data-ttu-id="a7db0-184">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns-and-setting-the-name-column"></a><span data-ttu-id="a7db0-185">Определение составного свойства KeyColumns и задание столбца имени</span><span class="sxs-lookup"><span data-stu-id="a7db0-185">Defining Composite KeyColumns and Setting the Name Column</span></span>  
 <span data-ttu-id="a7db0-186">Свойство **KeyColumns** содержит столбец или столбцы, представляющие ключ для атрибута.</span><span class="sxs-lookup"><span data-stu-id="a7db0-186">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="a7db0-187">В этой задаче будет определено составное свойство **KeyColumns**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-187">In this task, you will define composite **KeyColumns**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-english-month-name-attribute"></a><span data-ttu-id="a7db0-188">Определение составного свойства KeyColumns для атрибута English Month Name</span><span class="sxs-lookup"><span data-stu-id="a7db0-188">To define composite KeyColumns for the English Month Name attribute</span></span>  
  
1.  <span data-ttu-id="a7db0-189">Откройте измерение Date и перейдите на вкладку **Структура измерения** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-189">Open the **Dimension Structure** tab for the Date dimension.</span></span>  
  
2.  <span data-ttu-id="a7db0-190">На панели **Атрибуты** щелкните атрибут **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-190">In the **Attributes** pane, click the **English Month Name** attribute.</span></span>  
  
3.  <span data-ttu-id="a7db0-191">В окне **Свойства** щелкните в поле **KeyColumns** и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="a7db0-191">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="a7db0-192">В диалоговом окне **Ключевые столбцы** в списке **Доступные столбцы** выберите столбец **CalendarYear**и нажмите кнопку **>** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-192">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
5.  <span data-ttu-id="a7db0-193">Столбцы **EnglishMonthName** и **CalendarYear** отображаются в списке **Ключевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-193">The **EnglishMonthName** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
6.  <span data-ttu-id="a7db0-194">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-194">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="a7db0-195">Чтобы задать свойство **NameColumn** атрибута **EnglishMonthName** , щелкните поле **NameColumn** в окне свойств и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="a7db0-195">To set the **NameColumn** property of the **EnglishMonthName** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
8.  <span data-ttu-id="a7db0-196">В диалоговом окне **Столбец имени** в списке **Исходный столбец** выберите `MonthName` , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-196">In the **Name Column** dialog box, in the **Source Column** list, select `MonthName`, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="a7db0-197">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-197">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-quarter-attribute"></a><span data-ttu-id="a7db0-198">Определение составного свойства KeyColumns для атрибута Calendar Quarter</span><span class="sxs-lookup"><span data-stu-id="a7db0-198">To define composite KeyColumns for the Calendar Quarter attribute</span></span>  
  
1.  <span data-ttu-id="a7db0-199">На панели **Атрибуты** щелкните атрибут **Календарный квартал** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-199">In the **Attributes** pane, click the **Calendar Quarter** attribute.</span></span>  
  
2.  <span data-ttu-id="a7db0-200">В окне **Свойства** щелкните в поле **KeyColumns** и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="a7db0-200">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="a7db0-201">В диалоговом окне **Ключевые столбцы** в списке **Доступные столбцы** выберите столбец **CalendarYear**и нажмите кнопку **>** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-201">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="a7db0-202">Столбцы **CalendarQuarter** и **CalendarYear** отображаются в списке **Ключевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-202">The **CalendarQuarter** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="a7db0-203">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-203">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a7db0-204">Чтобы задать свойство **NameColumn** атрибута **Календарный квартал** , щелкните поле **NameColumn** в окне свойств и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="a7db0-204">To set the **NameColumn** property of the **Calendar Quarter** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="a7db0-205">В диалоговом окне **Столбец имени** в списке **Исходный столбец** выберите `CalendarQuarterDesc` , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-205">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarQuarterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a7db0-206">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-206">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-semester-attribute"></a><span data-ttu-id="a7db0-207">Определение составного свойства KeyColumns для атрибута Calendar Semester</span><span class="sxs-lookup"><span data-stu-id="a7db0-207">To define composite KeyColumns for the Calendar Semester attribute</span></span>  
  
1.  <span data-ttu-id="a7db0-208">На панели **Атрибуты** щелкните атрибут **Календарное полугодие** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-208">In the **Attributes** pane, click the **Calendar Semester** attribute.</span></span>  
  
2.  <span data-ttu-id="a7db0-209">В окне **Свойства** щелкните в поле **KeyColumns** и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="a7db0-209">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="a7db0-210">В диалоговом окне **Ключевые столбцы** выберите из списка **Доступные столбцы** столбец **CalendarYear**, а затем нажмите кнопку **>** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-210">In the **Key Columns** dialog box, in the **Available Columns** list, select the column, **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="a7db0-211">Столбцы **CalendarSemester** и **CalendarYear** отображаются в списке **Ключевые столбцы** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-211">The **CalendarSemester** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="a7db0-212">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-212">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a7db0-213">Чтобы задать свойство **NameColumn** атрибута **Календарное полугодие** , щелкните поле **NameColumn** в окне свойств и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="a7db0-213">To set the **NameColumn** property of the **Calendar Semester** attribute, click the **NameColumn** field in the property window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="a7db0-214">В диалоговом окне **Столбец имени** в списке **Исходный столбец** выберите `CalendarSemesterDesc` , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-214">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarSemesterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a7db0-215">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a7db0-215">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-and-viewing-the-changes"></a><span data-ttu-id="a7db0-216">Развертывание и просмотр изменений</span><span class="sxs-lookup"><span data-stu-id="a7db0-216">Deploying and Viewing the Changes</span></span>  
 <span data-ttu-id="a7db0-217">После изменения атрибутов и иерархий необходимо произвести развертывание произведенных изменений и повторную обработку связанных объектов, прежде чем эти изменения можно будет просмотреть.</span><span class="sxs-lookup"><span data-stu-id="a7db0-217">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-and-view-the-changes"></a><span data-ttu-id="a7db0-218">Развертывание и просмотр изменений</span><span class="sxs-lookup"><span data-stu-id="a7db0-218">To deploy and view the changes</span></span>  
  
1.  <span data-ttu-id="a7db0-219">В меню **Построение** среды [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-219">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="a7db0-220">Получив сообщение **Развертывание завершено успешно** , щелкните вкладку **браузер** в **конструкторе измерений** для `Date` измерения, а затем нажмите кнопку Повторное соединение на панели инструментов конструктора.</span><span class="sxs-lookup"><span data-stu-id="a7db0-220">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the `Date` dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="a7db0-221">В списке **Иерархия** выберите значение **Календарный квартал** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-221">Select **Calendar Quarter** from the **Hierarchy** list.</span></span> <span data-ttu-id="a7db0-222">Просмотрите элементы иерархии атрибута **Календарный квартал** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-222">Review the members in the **Calendar Quarter** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="a7db0-223">Обратите внимание, что имена элементов иерархии атрибута **Календарный квартал** выглядят понятнее и проще в использовании, так как для их отображения создано именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="a7db0-223">Notice that the names of the members of the **Calendar Quarter** attribute hierarchy are clearer and easier to use because you created a named calculation to use as the name.</span></span> <span data-ttu-id="a7db0-224">Теперь в иерархии атрибута **Календарный квартал** есть элементы для каждого квартала каждого года.</span><span class="sxs-lookup"><span data-stu-id="a7db0-224">Members now exist in the **Calendar Quarter** attribute hierarchy for each quarter in each year.</span></span> <span data-ttu-id="a7db0-225">Элементы не отсортированы в хронологическом порядке.</span><span class="sxs-lookup"><span data-stu-id="a7db0-225">The members are not sorted in chronological order.</span></span> <span data-ttu-id="a7db0-226">Вместо этого они отсортированы сначала по кварталам, а затем по годам.</span><span class="sxs-lookup"><span data-stu-id="a7db0-226">Instead they are sorted by quarter and then by year.</span></span> <span data-ttu-id="a7db0-227">В следующей задаче этого раздела требуется изменить поведение этой иерархии атрибута, чтобы отсортировать ее элементы сначала по годам, а затем по кварталам.</span><span class="sxs-lookup"><span data-stu-id="a7db0-227">In the next task in this topic, you will modify this behavior to sort the members of this attribute hierarchy by year and then by quarter.</span></span>  
  
4.  <span data-ttu-id="a7db0-228">Просмотрите элементы иерархий атрибутов **English Month Name** и **Календарное полугодие** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-228">Review the members of the **English Month Name** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="a7db0-229">Обратите внимание, что элементы этих иерархий также не отсортированы в хронологическом порядке.</span><span class="sxs-lookup"><span data-stu-id="a7db0-229">Notice that the members of these hierarchies are also not sorted in chronological order.</span></span> <span data-ttu-id="a7db0-230">Вместо этого они отсортированы сначала соответственно по месяцам или полугодиям, а затем — по годам.</span><span class="sxs-lookup"><span data-stu-id="a7db0-230">Instead, they are sorted by month or semester, respectively, and then by year.</span></span> <span data-ttu-id="a7db0-231">В следующей задаче этого раздела поведение этих иерархий атрибутов будет изменено, чтобы изменить порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="a7db0-231">In the next task in this topic, you will modify this behavior to change this sort order.</span></span>  
  
## <a name="changing-the-sort-order-by-modifying-composite-key-member-order"></a><span data-ttu-id="a7db0-232">Изменение порядка сортировки путем изменения порядка элементов составных ключей</span><span class="sxs-lookup"><span data-stu-id="a7db0-232">Changing the Sort Order by Modifying Composite Key Member Order</span></span>  
 <span data-ttu-id="a7db0-233">В этой задаче будет изменен порядок сортировки посредством изменения порядка ключей, составляющих составной ключ.</span><span class="sxs-lookup"><span data-stu-id="a7db0-233">In this task, you will change the sort order by changing the order of the keys that make up the composite key.</span></span>  
  
#### <a name="to-modify-the-composite-key-member-order"></a><span data-ttu-id="a7db0-234">Изменение порядка элементов составных ключей</span><span class="sxs-lookup"><span data-stu-id="a7db0-234">To modify the composite key member order</span></span>  
  
1.  <span data-ttu-id="a7db0-235">Откройте вкладку **Структура измерения** в конструкторе измерений для `Date` измерения, а затем выберите **Календарное полугодие** на панели **атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-235">Open the **Dimension Structure** tab of Dimension Designer for the `Date` dimension, and then select **Calendar Semester** in the **Attributes** pane.</span></span>  
  
2.  <span data-ttu-id="a7db0-236">В окне свойств просмотрите значение свойства **OrderBy** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-236">In the Properties window, review the value for the **OrderBy** property.</span></span> <span data-ttu-id="a7db0-237">Оно имеет значение **Ключ**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-237">It is set to **Key**.</span></span>  
  
     <span data-ttu-id="a7db0-238">Элементы иерархии атрибута **Календарное полугодие** отсортированы по значению ключа.</span><span class="sxs-lookup"><span data-stu-id="a7db0-238">The members of the **Calendar Semester** attribute hierarchy are sorted by their key value.</span></span> <span data-ttu-id="a7db0-239">При составном ключе сортировка ключей элементов ведется упорядочение сначала по значению первого ключа элемента, а затем — по значению второго ключа элемента.</span><span class="sxs-lookup"><span data-stu-id="a7db0-239">With a composite key, the ordering of the member keys is based first on the value of the first member key, and then on the value of the second member key.</span></span> <span data-ttu-id="a7db0-240">Иными словами, элементы иерархии атрибута **Календарное полугодие** отсортированы сначала по полугодиям, а затем по годам.</span><span class="sxs-lookup"><span data-stu-id="a7db0-240">In other words, the members of the **Calendar Semester** attribute hierarchy are sorted first by semester and then by year.</span></span>  
  
3.  <span data-ttu-id="a7db0-241">В окне свойств нажмите кнопку обзора (**...**), чтобы изменить значение свойства **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-241">In the Properties window, click the ellipsis browse button (**...**) to change the **KeyColumns** property value.</span></span>  
  
4.  <span data-ttu-id="a7db0-242">В списке **Ключевые столбцы** в диалоговом окне **Ключевые столбцы** выберите столбец **CalendarSemester** , а затем нажмите стрелку вниз, чтобы изменить порядок элементов составного ключа.</span><span class="sxs-lookup"><span data-stu-id="a7db0-242">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarSemester** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="a7db0-243">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-243">Click **OK**.</span></span>  
  
     <span data-ttu-id="a7db0-244">Теперь элементы этой иерархии атрибута отсортированы сначала по годам, а затем по полугодиям.</span><span class="sxs-lookup"><span data-stu-id="a7db0-244">The members of the attribute hierarchy are now sorted first by year and then by semester.</span></span>  
  
5.  <span data-ttu-id="a7db0-245">Выберите **Календарный квартал** на панели **Атрибуты** и нажмите кнопку обзора (**...**) для свойства **KeyColumns** в окне свойств.</span><span class="sxs-lookup"><span data-stu-id="a7db0-245">Select **Calendar Quarter** in the **Attributes** pane, and then click the ellipsis browse button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
6.  <span data-ttu-id="a7db0-246">В списке **Ключевые столбцы** диалогового окна **Ключевые столбцы** выделите столбец **CalendarQuarter** , а затем нажмите стрелку вниз, чтобы изменить порядок элементов составного ключа.</span><span class="sxs-lookup"><span data-stu-id="a7db0-246">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarQuarter** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="a7db0-247">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-247">Click **OK**.</span></span>  
  
     <span data-ttu-id="a7db0-248">Теперь элементы этой иерархии атрибута отсортированы сначала по годам, а затем по кварталам.</span><span class="sxs-lookup"><span data-stu-id="a7db0-248">The members of the attribute hierarchy are now sorted first by year and then by quarter.</span></span>  
  
7.  <span data-ttu-id="a7db0-249">На панели **Атрибуты** выберите элемент **English Month Name** , а затем в окне свойств нажмите кнопку с многоточием (**...**) для свойства **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-249">Select **English Month Name** in the **Attributes** pane, and then click the ellipsis button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
8.  <span data-ttu-id="a7db0-250">В списке **Ключевые столбцы** диалогового окна **Ключевые столбцы** выделите столбец **EnglishMonthName** , а затем нажмите стрелку вниз, чтобы изменить порядок элементов составного ключа.</span><span class="sxs-lookup"><span data-stu-id="a7db0-250">In the **Key Columns** list of the **Key Columns** dialog box, verify that **EnglishMonthName** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="a7db0-251">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-251">Click **OK**.</span></span>  
  
     <span data-ttu-id="a7db0-252">Теперь элементы этой иерархии атрибута отсортированы сначала по годам, а затем по месяцам.</span><span class="sxs-lookup"><span data-stu-id="a7db0-252">The members of the attribute hierarchy are now sorted first by year and then by month.</span></span>  
  
9. <span data-ttu-id="a7db0-253">В меню **Построение** среды [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="a7db0-253">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span> <span data-ttu-id="a7db0-254">После успешного завершения развертывания перейдите на вкладку **браузер** в конструкторе измерений для `Date` измерения.</span><span class="sxs-lookup"><span data-stu-id="a7db0-254">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the `Date` dimension.</span></span>  
  
10. <span data-ttu-id="a7db0-255">На панели инструментов вкладки **Браузер** нажмите кнопку повторного соединения.</span><span class="sxs-lookup"><span data-stu-id="a7db0-255">On the toolbar of the **Browser** tab, click the Reconnect button.</span></span>  
  
11. <span data-ttu-id="a7db0-256">Просмотрите элементы иерархий атрибутов **Календарный квартал** и **Календарное полугодие** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-256">Review the members of the **Calendar Quarter** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="a7db0-257">Обратите внимание, что теперь элементы этих иерархий атрибутов сортируются в хронологическом порядке, по годам, а затем по полугодиям или кварталам соответственно.</span><span class="sxs-lookup"><span data-stu-id="a7db0-257">Notice that the members of these hierarchies are now sorted in chronological order, by year and then by quarter or semester, respectively.</span></span>  
  
12. <span data-ttu-id="a7db0-258">Просмотрите элементы иерархии атрибута **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="a7db0-258">Review the members of the **English Month Name** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="a7db0-259">Обратите внимание, что теперь элементы этой иерархии атрибута сортируются сначала по годам, а затем по месяцам в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="a7db0-259">Notice that the members of the hierarchy are now sorted first by year and then alphabetically by month.</span></span> <span data-ttu-id="a7db0-260">Причина этого заключается в том, что столбец EnglishCalendarMonth в представлении источника данных имеет строковый тип данных, который основан на типе данных nvarchar базовой реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="a7db0-260">This is because the data type for the EnglishCalendarMonth column in the data source view is a string column, based on the nvarchar data type in the underlying relational database.</span></span> <span data-ttu-id="a7db0-261">Сведения о сортировке по месяцам хронологически внутри года см. в разделе [Сортировка элементов атрибута по вторичному атрибуту](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="a7db0-261">For information about how to enable the months to be sorted chronologically within each year, see [Sorting Attribute Members Based on a Secondary Attribute](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a7db0-262">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="a7db0-262">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a7db0-263">Просмотр развернутого куба</span><span class="sxs-lookup"><span data-stu-id="a7db0-263">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7db0-264">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7db0-264">See Also</span></span>  
 [<span data-ttu-id="a7db0-265">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="a7db0-265">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
