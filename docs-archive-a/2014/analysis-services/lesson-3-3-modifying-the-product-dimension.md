---
title: Изменение измерения Product | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8e3ffecd-7f40-41a8-8735-bc9858a310cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 04c0a778a73371dada92c9ff207a17366a2fbc7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665653"
---
# <a name="modifying-the-product-dimension"></a><span data-ttu-id="69aed-102">Изменение измерения Product</span><span class="sxs-lookup"><span data-stu-id="69aed-102">Modifying the Product Dimension</span></span>
  <span data-ttu-id="69aed-103">При выполнении задач этого раздела будут использованы именованные вычисления, чтобы предоставить понятные имена для линий товаров, определена иерархия в измерении «Продукт» и указано имя элемента «(Все)» для иерархии.</span><span class="sxs-lookup"><span data-stu-id="69aed-103">In the tasks in this topic, you use a named calculation to provide more descriptive names for the product lines, define a hierarchy in the Product dimension, and specify the (All) member name for the hierarchy.</span></span> <span data-ttu-id="69aed-104">Также атрибуты будут сгруппированы в папки отображения.</span><span class="sxs-lookup"><span data-stu-id="69aed-104">You also group attributes into display folders.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="69aed-105">Добавление именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="69aed-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="69aed-106">К таблице в представлении источника данных может быть добавлено именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="69aed-106">You can add a named calculation to a table in a data source view.</span></span> <span data-ttu-id="69aed-107">В следующей задаче будет создано именованное вычисление, которое отображает полное наименование линейки продуктов.</span><span class="sxs-lookup"><span data-stu-id="69aed-107">In the following task, you create a named calculation that displays the full product line name.</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="69aed-108">Добавление именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="69aed-108">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="69aed-109">Чтобы открыть представление источника данных **Adventure Works DW 2012** , дважды щелкните **Adventure Works DW 2012** в папке **Представления источников данных** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="69aed-109">To open the **Adventure Works DW 2012** data source view, double-click **Adventure Works DW 2012** in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="69aed-110">В нижней части панели диаграмм щелкните правой кнопкой мыши заголовок таблицы **Продукт** и выберите команду **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="69aed-110">In the bottom of the diagram pane, right-click the **Product** table header, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="69aed-111">В диалоговом окне **Создание именованного вычисления** введите `ProductLineName` в поле **имя столбца** .</span><span class="sxs-lookup"><span data-stu-id="69aed-111">In the **Create Named Calculation** dialog box, type `ProductLineName` in the **Column name** box.</span></span>  
  
4.  <span data-ttu-id="69aed-112">В поле **Выражение** введите или скопируйте и вставьте следующую инструкцию **CASE** :</span><span class="sxs-lookup"><span data-stu-id="69aed-112">In the **Expression** box, type or copy and paste the following **CASE** statement:</span></span>  
  
    ```  
    CASE ProductLine  
       WHEN 'M' THEN 'Mountain'  
       WHEN 'R' THEN 'Road'  
       WHEN 'S' THEN 'Accessory'  
       WHEN 'T' THEN 'Touring'  
       ELSE 'Components'  
    END  
    ```  
  
     <span data-ttu-id="69aed-113">Эта инструкция **CASE** для каждой строки товара в кубе создает понятные имена.</span><span class="sxs-lookup"><span data-stu-id="69aed-113">This **CASE** statement creates user-friendly names for each product line in the cube.</span></span>  
  
5.  <span data-ttu-id="69aed-114">Нажмите кнопку **ОК** , чтобы создать `ProductLineName` именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="69aed-114">Click **OK** to create the `ProductLineName` named calculation.</span></span> <span data-ttu-id="69aed-115">Возможно, потребуется подождать.</span><span class="sxs-lookup"><span data-stu-id="69aed-115">You might need to wait.</span></span>  
  
6.  <span data-ttu-id="69aed-116">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="69aed-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="modifying-the-namecolumn-property-of-an-attribute"></a><span data-ttu-id="69aed-117">Изменение свойства NameColumn атрибута</span><span class="sxs-lookup"><span data-stu-id="69aed-117">Modifying the NameColumn Property of an Attribute</span></span>  
  
#### <a name="to-modify-the-namecolumn-property-value-of-an-attribute"></a><span data-ttu-id="69aed-118">Изменение значения свойства NameColumn атрибута</span><span class="sxs-lookup"><span data-stu-id="69aed-118">To modify the NameColumn property value of an attribute</span></span>  
  
1.  <span data-ttu-id="69aed-119">В конструкторе измерений откройте измерение Product.</span><span class="sxs-lookup"><span data-stu-id="69aed-119">Switch to Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="69aed-120">Для этого дважды щелкните измерение **Продукт** в узле **Измерения** обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="69aed-120">To do this, double-click the **Product** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="69aed-121">На панели **Атрибуты** вкладки **Структура измерения** выберите **Product Line**.</span><span class="sxs-lookup"><span data-stu-id="69aed-121">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Line**.</span></span>  
  
3.  <span data-ttu-id="69aed-122">В окно свойств в правой части экрана щелкните поле свойства **NameColumn** в нижней части окна, а затем нажмите кнопку обзора (**...**), чтобы открыть диалоговое окно **Столбец имени** .</span><span class="sxs-lookup"><span data-stu-id="69aed-122">In the Properties window on the right side of the screen, click the **NameColumn** property field at the bottom of the window, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span> <span data-ttu-id="69aed-123">Возможно, потребуется перейти на вкладку **Свойства** в правой части окна, чтобы открыть окно "Свойства".</span><span class="sxs-lookup"><span data-stu-id="69aed-123">(You might need to click the **Properties** tab on the right side of the screen to open the Properties window.</span></span>  
  
4.  <span data-ttu-id="69aed-124">Выберите `ProductLineName` в нижней части списка **Исходный столбец** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="69aed-124">Select `ProductLineName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="69aed-125">Теперь поле NameColumn содержит текст **Product.ProductLineName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="69aed-125">The NameColumn field now contains the text, **Product.ProductLineName (WChar)**.</span></span> <span data-ttu-id="69aed-126">После этого элементы иерархии атрибута **Product Line** будут содержать не сокращенное, а полное наименование линейки продуктов.</span><span class="sxs-lookup"><span data-stu-id="69aed-126">The members of the **Product Line** attribute hierarchy now display the full name of the product line instead of an abbreviated product line name.</span></span>  
  
5.  <span data-ttu-id="69aed-127">На панели **Атрибуты** вкладки **Структура измерения** выберите **Product Key**.</span><span class="sxs-lookup"><span data-stu-id="69aed-127">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Key**.</span></span>  
  
6.  <span data-ttu-id="69aed-128">В окно свойств щелкните поле свойства **NameColumn** , а затем нажмите кнопку обзора (**...**), чтобы открыть диалоговое окно **Столбец имени** .</span><span class="sxs-lookup"><span data-stu-id="69aed-128">In the Properties window, click the **NameColumn** property field, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
7.  <span data-ttu-id="69aed-129">Выберите в списке **Исходный столбец** значение **EnglishProductName** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="69aed-129">Select **EnglishProductName** in the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="69aed-130">Теперь поле NameColumn содержит текст **Product.EnglishProductName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="69aed-130">The NameColumn field now contains the text, **Product.EnglishProductName (WChar)**.</span></span>  
  
8.  <span data-ttu-id="69aed-131">В окно свойств прокрутите вниз, щелкните поле свойства **имя** и введите `Product Name` .</span><span class="sxs-lookup"><span data-stu-id="69aed-131">In the Properties window, scroll up, click the **Name** property field, and then type `Product Name`.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="69aed-132">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="69aed-132">Creating a Hierarchy</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="69aed-133">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="69aed-133">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="69aed-134">Перетащите атрибут **Product Line** с панели **Атрибуты** на панель **Иерархии** .</span><span class="sxs-lookup"><span data-stu-id="69aed-134">Drag the **Product Line** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="69aed-135">Перетащите атрибут **Model Name** с панели **Атрибуты** в ячейку **\<new level>** на панели **Иерархии** под уровнем **Product Line** .</span><span class="sxs-lookup"><span data-stu-id="69aed-135">Drag the **Model Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Product Line** level.</span></span>  
  
3.  <span data-ttu-id="69aed-136">Перетащите `Product Name` атрибут из панели **атрибуты** в **\<new level>** ячейку на панели **иерархии** под уровнем **имя модели** .</span><span class="sxs-lookup"><span data-stu-id="69aed-136">Drag the `Product Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Model Name** level.</span></span> <span data-ttu-id="69aed-137">(«Ключ продукта» был переименован в «Имя продукта» в предыдущем разделе.)</span><span class="sxs-lookup"><span data-stu-id="69aed-137">(You renamed Product Key to Product Name in the previous section.)</span></span>  
  
4.  <span data-ttu-id="69aed-138">На панели **иерархии** вкладки **Структура измерения** щелкните правой кнопкой мыши строку заголовка иерархии **Иерархия** , выберите команду **Переименовать**, а затем введите `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="69aed-138">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Product Model Lines`.</span></span>  
  
     <span data-ttu-id="69aed-139">Теперь имя иерархии — `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="69aed-139">The name of the hierarchy is now `Product Model Lines`.</span></span>  
  
5.  <span data-ttu-id="69aed-140">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="69aed-140">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="specifying-folder-names-and-all-member-names"></a><span data-ttu-id="69aed-141">Определение имен папок и имени элемента «Все»</span><span class="sxs-lookup"><span data-stu-id="69aed-141">Specifying Folder Names and All Member Names</span></span>  
  
#### <a name="to-specify-the-folder-and-member-names"></a><span data-ttu-id="69aed-142">Указание имен папок и элементов</span><span class="sxs-lookup"><span data-stu-id="69aed-142">To specify the folder and member names</span></span>  
  
1.  <span data-ttu-id="69aed-143">На панели **Атрибуты** выберите следующие атрибуты (щелкните каждый из них, удерживая нажатой клавишу CTRL):</span><span class="sxs-lookup"><span data-stu-id="69aed-143">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="69aed-144">**Класс**</span><span class="sxs-lookup"><span data-stu-id="69aed-144">**Class**</span></span>  
  
    -   <span data-ttu-id="69aed-145">**Цвет**</span><span class="sxs-lookup"><span data-stu-id="69aed-145">**Color**</span></span>  
  
    -   <span data-ttu-id="69aed-146">**Дни производства**</span><span class="sxs-lookup"><span data-stu-id="69aed-146">**Days To Manufacture**</span></span>  
  
    -   <span data-ttu-id="69aed-147">**Reorder Point**</span><span class="sxs-lookup"><span data-stu-id="69aed-147">**Reorder Point**</span></span>  
  
    -   <span data-ttu-id="69aed-148">**Safety Stock Level**</span><span class="sxs-lookup"><span data-stu-id="69aed-148">**Safety Stock Level**</span></span>  
  
    -   <span data-ttu-id="69aed-149">**Размер**</span><span class="sxs-lookup"><span data-stu-id="69aed-149">**Size**</span></span>  
  
    -   <span data-ttu-id="69aed-150">**Size Range**</span><span class="sxs-lookup"><span data-stu-id="69aed-150">**Size Range**</span></span>  
  
    -   <span data-ttu-id="69aed-151">**Style**</span><span class="sxs-lookup"><span data-stu-id="69aed-151">**Style**</span></span>  
  
    -   <span data-ttu-id="69aed-152">**Weight**</span><span class="sxs-lookup"><span data-stu-id="69aed-152">**Weight**</span></span>  
  
2.  <span data-ttu-id="69aed-153">В поле свойства **AttributeHierarchyDisplayFolder** в окно свойств введите `Stocking` .</span><span class="sxs-lookup"><span data-stu-id="69aed-153">In the **AttributeHierarchyDisplayFolder** property field in the Properties window, type `Stocking`.</span></span>  
  
     <span data-ttu-id="69aed-154">Атрибуты сгруппированы в единую папку отображения.</span><span class="sxs-lookup"><span data-stu-id="69aed-154">You have now grouped these attributes into a single display folder.</span></span>  
  
3.  <span data-ttu-id="69aed-155">На панели **Атрибуты** выберите следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="69aed-155">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="69aed-156">**Dealer Price**</span><span class="sxs-lookup"><span data-stu-id="69aed-156">**Dealer Price**</span></span>  
  
    -   <span data-ttu-id="69aed-157">**List Price**</span><span class="sxs-lookup"><span data-stu-id="69aed-157">**List Price**</span></span>  
  
    -   <span data-ttu-id="69aed-158">**Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="69aed-158">**Standard Cost**</span></span>  
  
4.  <span data-ttu-id="69aed-159">В ячейке свойства **AttributeHierarchyDisplayFolder** в окно свойств введите `Financial` .</span><span class="sxs-lookup"><span data-stu-id="69aed-159">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `Financial`.</span></span>  
  
     <span data-ttu-id="69aed-160">Атрибуты сгруппированы во вторую папку отображения.</span><span class="sxs-lookup"><span data-stu-id="69aed-160">You have now grouped these attributes into a second display folder.</span></span>  
  
5.  <span data-ttu-id="69aed-161">На панели **Атрибуты** выберите следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="69aed-161">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="69aed-162">**Дата окончания**</span><span class="sxs-lookup"><span data-stu-id="69aed-162">**End Date**</span></span>  
  
    -   <span data-ttu-id="69aed-163">**Дата начала**</span><span class="sxs-lookup"><span data-stu-id="69aed-163">**Start Date**</span></span>  
  
    -   <span data-ttu-id="69aed-164">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="69aed-164">**Status**</span></span>  
  
6.  <span data-ttu-id="69aed-165">В ячейке свойства **AttributeHierarchyDisplayFolder** в окно свойств введите `History` .</span><span class="sxs-lookup"><span data-stu-id="69aed-165">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `History`.</span></span>  
  
     <span data-ttu-id="69aed-166">Атрибуты сгруппированы в третью папку отображения.</span><span class="sxs-lookup"><span data-stu-id="69aed-166">You have now grouped these attributes into a third display folder.</span></span>  
  
7.  <span data-ttu-id="69aed-167">Выберите `Product Model Lines` иерархию на панели **иерархии** , а затем измените свойство **AllMemberName** в окно свойств на `All Products` .</span><span class="sxs-lookup"><span data-stu-id="69aed-167">Select the `Product Model Lines` hierarchy in the **Hierarchies** pane, and then change the **AllMemberName** property in the Properties window to `All Products`.</span></span>  
  
8.  <span data-ttu-id="69aed-168">Щелкните открытую область панели **иерархии** , а затем измените свойство **AttributeAllMemberName** в верхней части окно свойств на `All Products` .</span><span class="sxs-lookup"><span data-stu-id="69aed-168">Click an open area of the **Hierarchies** pane, and then change the **AttributeAllMemberName** property at the top of the Properties window to `All Products`.</span></span>  
  
     <span data-ttu-id="69aed-169">Щелкнув рабочую область, можно изменять свойства самого измерения Product.</span><span class="sxs-lookup"><span data-stu-id="69aed-169">Clicking an open area lets you modify properties of the Product dimension itself.</span></span> <span data-ttu-id="69aed-170">Также можно щелкнуть значок измерения **Продукт** в начале списка атрибутов на панели **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="69aed-170">You could also click **Product** at the top of the attributes list in the **Attributes** pane.</span></span>  
  
9. <span data-ttu-id="69aed-171">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="69aed-171">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="69aed-172">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="69aed-172">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="69aed-173">Необходимо определять связи между атрибутами, если базовые данные это поддерживают.</span><span class="sxs-lookup"><span data-stu-id="69aed-173">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="69aed-174">Определение связей между атрибутами ускоряет обработку измерений, секций и запросов.</span><span class="sxs-lookup"><span data-stu-id="69aed-174">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="69aed-175">Дополнительные сведения см. в разделах [Определение связей атрибутов](multidimensional-models/attribute-relationships-define.md) и [Связи атрибутов](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="69aed-175">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="69aed-176">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="69aed-176">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="69aed-177">В окне **Конструктор измерений** для измерения Product откройте вкладку **Связи атрибутов** .</span><span class="sxs-lookup"><span data-stu-id="69aed-177">In the **Dimension Designer** for the Product dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="69aed-178">На диаграмме щелкните правой кнопкой мыши атрибут **имя модели** и выберите команду **создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="69aed-178">In the diagram, right-click the **Model Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="69aed-179">В диалоговом окне **Создание связи атрибутов** поле **Исходный атрибут** имеет значение **Имя модели**.</span><span class="sxs-lookup"><span data-stu-id="69aed-179">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Model Name**.</span></span> <span data-ttu-id="69aed-180">Задайте для поля **Связанный атрибут** значение **Линейка продуктов**.</span><span class="sxs-lookup"><span data-stu-id="69aed-180">Set the **Related Attribute** to **Product Line**.</span></span>  
  
     <span data-ttu-id="69aed-181">В списке **Тип связи** оставьте выбранным тип **Гибкая** , так как связи между элементами могут измениться с течением времени.</span><span class="sxs-lookup"><span data-stu-id="69aed-181">In the **Relationship type** list, leave the relationship type set to **Flexible** because relationships between the members might change over time.</span></span> <span data-ttu-id="69aed-182">Например, модель товара со временем могла быть перенесена в другую линию товаров.</span><span class="sxs-lookup"><span data-stu-id="69aed-182">For example, a product model might eventually be moved to a different product line.</span></span>  
  
4.  <span data-ttu-id="69aed-183">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="69aed-183">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="69aed-184">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="69aed-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="reviewing-product-dimension-changes"></a><span data-ttu-id="69aed-185">Просмотр изменений в измерении Product</span><span class="sxs-lookup"><span data-stu-id="69aed-185">Reviewing Product Dimension Changes</span></span>  
  
#### <a name="to-review-the-product-dimension-changes"></a><span data-ttu-id="69aed-186">Просмотр изменений в измерении Product</span><span class="sxs-lookup"><span data-stu-id="69aed-186">To review the Product dimension changes</span></span>  
  
1.  <span data-ttu-id="69aed-187">В меню **Построение** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="69aed-187">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="69aed-188">Получив сообщение **Развертывание выполнено успешно** , перейдите на вкладку **Браузер** окна **Конструктор измерений** для измерения **Продукт** и нажмите на панели инструментов кнопку повторного соединения.</span><span class="sxs-lookup"><span data-stu-id="69aed-188">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the **Product** dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="69aed-189">Убедитесь, что `Product Model Lines` в списке **Иерархия** выбрано значение, а затем разверните `All Products` .</span><span class="sxs-lookup"><span data-stu-id="69aed-189">Verify that `Product Model Lines` is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>  
  
     <span data-ttu-id="69aed-190">Обратите внимание, что имя элемента **все** отображается как `All Products` .</span><span class="sxs-lookup"><span data-stu-id="69aed-190">Notice that the name of the **All** member appears as `All Products`.</span></span> <span data-ttu-id="69aed-191">Это связано с тем, что свойство **AllMemberName** для иерархии было изменено на `All Products` более раннее занятие.</span><span class="sxs-lookup"><span data-stu-id="69aed-191">This is because you changed the **AllMemberName** property for the hierarchy to `All Products` earlier in the lesson.</span></span> <span data-ttu-id="69aed-192">Кроме того, все элементы уровня **Product Line** теперь имеют понятные имена, а не однобуквенные сокращения.</span><span class="sxs-lookup"><span data-stu-id="69aed-192">Also, the members of the **Product Line** level now have user-friendly names, instead of single-letter abbreviations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="69aed-193">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="69aed-193">Next Task in Lesson</span></span>  
 [<span data-ttu-id="69aed-194">Изменение измерения Date</span><span class="sxs-lookup"><span data-stu-id="69aed-194">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="69aed-195">См. также:</span><span class="sxs-lookup"><span data-stu-id="69aed-195">See Also</span></span>  
 <span data-ttu-id="69aed-196">[Определение именованных вычислений в представлении источника данных &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="69aed-196">[Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span></span>  
 <span data-ttu-id="69aed-197">[Создание определяемых пользователем иерархий](multidimensional-models/user-defined-hierarchies-create.md) </span><span class="sxs-lookup"><span data-stu-id="69aed-197">[Create User-Defined Hierarchies](multidimensional-models/user-defined-hierarchies-create.md) </span></span>  
 [<span data-ttu-id="69aed-198">Настройка уровня "Все" для иерархий атрибутов</span><span class="sxs-lookup"><span data-stu-id="69aed-198">Configure the &#40;All&#41; Level for Attribute Hierarchies</span></span>](multidimensional-models/database-dimensions-configure-the-all-level-for-attribute-hierarchies.md)  
  
  
