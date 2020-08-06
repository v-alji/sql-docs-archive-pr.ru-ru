---
title: Определение свойств неизвестного элемента и обработки значений NULL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d9abb09c-9bfa-4e32-b530-8590e4383566
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdd6504bec4f129f64d9bef6f6b0138e917888e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658528"
---
# <a name="defining-the-unknown-member-and-null-processing-properties"></a><span data-ttu-id="b465a-102">Определение свойств Unknown Member и Null Processing</span><span class="sxs-lookup"><span data-stu-id="b465a-102">Defining the Unknown Member and Null Processing Properties</span></span>
  <span data-ttu-id="b465a-103">В процессе обработки измерения службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] его атрибуты заполняются всеми уникальными значениями, полученными из базовых столбцов представлений и таблиц в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="b465a-103">When [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] processes a dimension, all the distinct values from the underlying columns in the tables, or views in the data source view, populate the attributes in the dimension.</span></span> <span data-ttu-id="b465a-104">Если при обработке службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] обнаруживают значение NULL, по умолчанию оно преобразуется в нулевое значение для числовых столбцов или в пустую строку — для строковых.</span><span class="sxs-lookup"><span data-stu-id="b465a-104">If [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] encounters a null value during processing, by default, it converts this null to a zero for numeric columns or to an empty string for string columns.</span></span> <span data-ttu-id="b465a-105">Можно изменить значения по умолчанию или преобразовывать значения NULL в процессе извлечения, преобразования или загрузки данных (если они выполняются) из базового реляционного хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="b465a-105">You can modify the default settings or convert null values in your extract, transform, and load process (if any) of the underlying relational data warehouse.</span></span> <span data-ttu-id="b465a-106">Кроме того, службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] можно настроить для преобразования значения NULL в указанное значение настройкой трех свойств: **UnknownMember** и **UnknownMemberName** для измерения и **NullProcessing** для ключевого атрибута измерения.</span><span class="sxs-lookup"><span data-stu-id="b465a-106">Additionally, you can have [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] convert the null value to a designated value by configuring three properties: the **UnknownMember** and **UnknownMemberName** properties for the dimension, and the **NullProcessing** property for the dimension's key attribute.</span></span>

 <span data-ttu-id="b465a-107">Мастер измерений и мастер кубов включают эти свойства в том случае, если ключевой атрибут измерения допускает значения NULL или корневой атрибут измерения, связанного по схеме «снежинка», основан на столбце, который допускает значения NULL.</span><span class="sxs-lookup"><span data-stu-id="b465a-107">The Dimension Wizard and the Cube Wizard will enable these properties for you based on whether the key attribute of a dimension is nullable or the root attribute of a snowflake dimension is based on a nullable column.</span></span> <span data-ttu-id="b465a-108">В этих случаях свойству **NullProcessing** ключевого атрибута будет присвоено значение **UnknownMember** , а свойству **UnknownMember** — значение **Visible**.</span><span class="sxs-lookup"><span data-stu-id="b465a-108">In these cases, the **NullProcessing** property of the key attribute will be set to **UnknownMember** and the **UnknownMember** property will be set to **Visible**.</span></span>

 <span data-ttu-id="b465a-109">Однако при добавочной сборке измерений, связанных по схеме "снежинка" (как в измерении Product на занятиях учебника), или при определении измерений с помощью конструктора измерений и их последующей интеграции в куб может потребоваться ручная установка свойств **UnknownMember** и **NullProcessing** .</span><span class="sxs-lookup"><span data-stu-id="b465a-109">However, when you build snowflaked dimensions incrementally, as we are doing with the Product dimension in this tutorial, or when you define dimensions using Dimension Designer and then incorporate these existing dimensions into a cube, the **UnknownMember** and **NullProcessing** properties might need to be set manually.</span></span>

 <span data-ttu-id="b465a-110">В задачах этого раздела будут добавлены атрибуты категории и подкатегории товара в измерение Product из таблиц, связанных по схеме «снежинка», которые, в свою очередь, будут добавлены в представление источника данных [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW.</span><span class="sxs-lookup"><span data-stu-id="b465a-110">In the tasks in this topic, you will add the product category and product subcategory attributes to the Product dimension from snowflaked tables that you will add to the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW data source view.</span></span> <span data-ttu-id="b465a-111">Затем включите свойство **UnknownMember** для измерения Product, укажите в `Assembly Components` качестве значения свойства **UnknownMemberName** , свяжите `Subcategory` `Category` атрибуты и с атрибутом Product Name, а затем определите пользовательскую обработку ошибок для ключевого атрибута элемента, связывающего таблицы по схеме «снежинка».</span><span class="sxs-lookup"><span data-stu-id="b465a-111">You will then enable the **UnknownMember** property for the Product dimension, specify `Assembly Components` as the value for the **UnknownMemberName** property, relate the `Subcategory` and `Category` attributes to the product name attribute, and then define custom error handling for the member key attribute that links the snowflaked tables.</span></span>

> [!NOTE]
>  <span data-ttu-id="b465a-112">Если изначально куб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial был определен с помощью мастера кубов, при добавлении атрибутов Subcategory и Category эти шаги будут выполнены автоматически.</span><span class="sxs-lookup"><span data-stu-id="b465a-112">If you have added the Subcategory and Category attributes when you originally defined the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube using the Cube Wizard, these steps would have been performed for you automatically.</span></span>

## <a name="reviewing-error-handling-and-unknown-member-properties-in-the-product-dimension"></a><span data-ttu-id="b465a-113">Просмотр свойств обработки ошибок и неизвестного элемента в измерении Product</span><span class="sxs-lookup"><span data-stu-id="b465a-113">Reviewing Error Handling and Unknown Member Properties in the Product Dimension</span></span>

1.  <span data-ttu-id="b465a-114">Переключитесь в конструкторе измерений на измерение **Product** , перейдите на вкладку **Структура измерения** и выберите на панели **Атрибуты** элемент **Product** .</span><span class="sxs-lookup"><span data-stu-id="b465a-114">Switch to Dimension Designer for the **Product** dimension, click the **Dimension Structure** tab, and then select **Product** in the **Attributes** pane.</span></span>

     <span data-ttu-id="b465a-115">Теперь можно просматривать и изменять свойства самого измерения.</span><span class="sxs-lookup"><span data-stu-id="b465a-115">This enables you to view and modify the properties of the dimension itself.</span></span>

2.  <span data-ttu-id="b465a-116">В окне "Свойства" просмотрите свойства **UnknownMember** и **UnknownMemberName** .</span><span class="sxs-lookup"><span data-stu-id="b465a-116">In the Properties window, review the **UnknownMember** and **UnknownMemberName** properties.</span></span>

     <span data-ttu-id="b465a-117">Обратите внимание, что свойство **UnknownMember** отключено, так как для него указано значение **Нет** вместо **Видимый** или **Скрытый**, и что для свойства **UnknownMemberName** имя не задано.</span><span class="sxs-lookup"><span data-stu-id="b465a-117">Notice that the **UnknownMember** property is not enabled, because its value is set to **None** instead of **Visible** or **Hidden**, and that no name is specified for the **UnknownMemberName** property.</span></span>

3.  <span data-ttu-id="b465a-118">В окне свойств в ячейке свойств **ErrorConfiguration** выберите **(пользовательский)** и раскройте коллекцию свойств **ErrorConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b465a-118">In the Properties window, select **(custom)** in the **ErrorConfiguration** property cell, and then expand the **ErrorConfiguration** properties collection.</span></span>

     <span data-ttu-id="b465a-119">Выбор значения **(пользовательский)** для свойства **ErrorConfiguration** позволяет просмотреть используемые по умолчанию настройки конфигурации обработки ошибок; настройки при этом не изменяются.</span><span class="sxs-lookup"><span data-stu-id="b465a-119">Setting the **ErrorConfiguration** property to **(custom)** allows you to view the default error configuration settings - it does not change any settings.</span></span>

4.  <span data-ttu-id="b465a-120">Просмотрите свойства конфигурации ошибок ключа и ошибок ключа NULL, однако не вносите изменения.</span><span class="sxs-lookup"><span data-stu-id="b465a-120">Review the key and null key error configuration properties, but do not make any changes.</span></span>

     <span data-ttu-id="b465a-121">Обратите внимание, что по умолчанию при преобразовании ключа NULL в неизвестный элемент ошибка обработки, связанная с этим преобразованием, пропускается.</span><span class="sxs-lookup"><span data-stu-id="b465a-121">Notice that, by default, when null keys are converted to the unknown member and the processing error associated with this conversion is ignored.</span></span>

     <span data-ttu-id="b465a-122">На рисунке ниже показаны параметры свойств в коллекции свойств **ErrorConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b465a-122">The following image shows the property settings for the **ErrorConfiguration** properties collection.</span></span>

     <span data-ttu-id="b465a-123">![Коллекция свойств ErrorConfiguration](../../2014/tutorials/media/l4-productdimensionerrorconfig-1.gif "Коллекция свойств ErrorConfiguration")</span><span class="sxs-lookup"><span data-stu-id="b465a-123">![ErrorConfiguration property collection](../../2014/tutorials/media/l4-productdimensionerrorconfig-1.gif "ErrorConfiguration property collection")</span></span>

5.  <span data-ttu-id="b465a-124">Перейдите на вкладку **браузер** , убедитесь в том, что в списке **Иерархия** выбран пункт **линии модели продукта** , а затем разверните `All Products` .</span><span class="sxs-lookup"><span data-stu-id="b465a-124">Click the **Browser** tab, verify that **Product Model Lines** is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>

     <span data-ttu-id="b465a-125">Обратите внимание на пять элементов уровня Product Line.</span><span class="sxs-lookup"><span data-stu-id="b465a-125">Notice the five members of the Product Line level.</span></span>

6.  <span data-ttu-id="b465a-126">Разверните узел **Components**, а затем разверните немаркированный элемент уровня **Model Name** .</span><span class="sxs-lookup"><span data-stu-id="b465a-126">Expand **Components**, and then expand the unlabeled member of the **Model Name** level.</span></span>

     <span data-ttu-id="b465a-127">Этот уровень содержит компоненты сборки, используемые при построении других компонентов, начиная с продукта **Adjustable Race** , как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="b465a-127">This level contains the assembly components that are used when building other components, starting with the **Adjustable Race** product, as shown in the following image.</span></span>

     <span data-ttu-id="b465a-128">![Компоненты сборки для создания других компонентов](../../2014/tutorials/media/l4-productdimensionerrorconfig-2.gif "Компоненты сборки для создания других компонентов")</span><span class="sxs-lookup"><span data-stu-id="b465a-128">![Assembly components used to build other components](../../2014/tutorials/media/l4-productdimensionerrorconfig-2.gif "Assembly components used to build other components")</span></span>

## <a name="defining-attributes-from-snowflaked-tables-and-a-product-category-user-defined-hierarchy"></a><span data-ttu-id="b465a-129">Определение атрибутов из связанных по схеме «снежинка» таблиц и пользовательской иерархии Product Category</span><span class="sxs-lookup"><span data-stu-id="b465a-129">Defining Attributes from Snowflaked Tables and a Product Category User-Defined Hierarchy</span></span>

1.  <span data-ttu-id="b465a-130">Откройте в конструкторе представлений источников данных представление источника данных [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW, выберите **Reseller Sales** на панели **Организатор диаграмм** , а затем выберите команду **Добавить или удалить объекты** в меню **Представление источников данных** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b465a-130">Open Data Source View Designer for the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW data source view, select **Reseller Sales** in the **Diagram Organizer** pane, and then click **Add/Remove Objects** on the **Data Source View** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>

     <span data-ttu-id="b465a-131">Откроется диалоговое окно **Добавление или удаление таблиц** .</span><span class="sxs-lookup"><span data-stu-id="b465a-131">The **Add/Remove Tables** dialog box opens.</span></span>

2.  <span data-ttu-id="b465a-132">В списке **Включенные объекты** выберите **DimProduct (dbo)**, а затем нажмите кнопку **Добавить связанные таблицы**.</span><span class="sxs-lookup"><span data-stu-id="b465a-132">In the **Included objects** list, select **DimProduct (dbo)**, and then click **Add Related Tables**.</span></span>

     <span data-ttu-id="b465a-133">Будут добавлены объекты **DimProductSubcategory (dbo)** и **FactProductInventory (dbo)** .</span><span class="sxs-lookup"><span data-stu-id="b465a-133">Both **DimProductSubcategory (dbo)** and **FactProductInventory (dbo)** are added.</span></span> <span data-ttu-id="b465a-134">Удалите **FactProductInventory (dbo)** , чтобы в список **Включенные объекты** была добавлена только таблица **DimProductSubcategory (dbo)** .</span><span class="sxs-lookup"><span data-stu-id="b465a-134">Remove **FactProductInventory (dbo)** so that just the **DimProductSubcategory (dbo)** table is added to the **Included objects** list.</span></span>

3.  <span data-ttu-id="b465a-135">Повторно нажмите кнопку **Добавить связанные таблицы** при выбранной по умолчанию (как последняя добавленная) таблице **DimProductSubcategory (dbo)** .</span><span class="sxs-lookup"><span data-stu-id="b465a-135">With the **DimProductSubcategory (dbo)** table selected by default as the table most recently added, click **Add Related Tables** again.</span></span>

     <span data-ttu-id="b465a-136">Таблица **DimProductCategory (dbo)** будет добавлена в список **Включенные объекты** .</span><span class="sxs-lookup"><span data-stu-id="b465a-136">The **DimProductCategory (dbo)** table is added to the **Included objects** list.</span></span>

4.  <span data-ttu-id="b465a-137">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b465a-137">Click **OK**.</span></span>

5.  <span data-ttu-id="b465a-138">В меню **Формат** среды [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]последовательно выберите команды **Автоматический макет**и **Диаграмма**.</span><span class="sxs-lookup"><span data-stu-id="b465a-138">On the **Format** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], point to **Auto Layout**, and then click **Diagram**.</span></span>

     <span data-ttu-id="b465a-139">Обратите внимание, что таблицы **DimProductSubcategory (dbo)** и **DimProductCategory (dbo)** связаны друг с другом, а также с таблицей **ResellerSales** через таблицу **Product** .</span><span class="sxs-lookup"><span data-stu-id="b465a-139">Notice that the **DimProductSubcategory (dbo)** table and **DimProductCategory (dbo)** table are linked to each other, and also to the **ResellerSales** table through the **Product** table.</span></span>

6.  <span data-ttu-id="b465a-140">Перейдите в конструкторе измерений к измерению **Product** и откройте вкладку **Структура измерения** .</span><span class="sxs-lookup"><span data-stu-id="b465a-140">Switch to Dimension Designer for the **Product** dimension, and then click the **Dimension Structure** tab.</span></span>

7.  <span data-ttu-id="b465a-141">Щелкните правой кнопкой мыши панель **Представление источника данных** и выберите команду **Показать все таблицы**.</span><span class="sxs-lookup"><span data-stu-id="b465a-141">Right-click anywhere in the **Data Source View** pane, and then click **Show All Tables**.</span></span>

8.  <span data-ttu-id="b465a-142">На панели **Представление источника данных** найдите таблицу **DimProductCategory** , щелкните в ней правой кнопкой мыши столбец **ProductCategoryKey** и выберите команду **Создать атрибут из столбца**.</span><span class="sxs-lookup"><span data-stu-id="b465a-142">In the **Data Source View** pane, locate the **DimProductCategory** table, right-click **ProductCategoryKey** in that table, and then click **New Attribute from Column**.</span></span>

9. <span data-ttu-id="b465a-143">На панели **атрибуты** измените имя этого нового атрибута на `Category` .</span><span class="sxs-lookup"><span data-stu-id="b465a-143">In the **Attributes** pane, change the name of this new attribute to `Category`.</span></span>

10. <span data-ttu-id="b465a-144">В окно свойств щелкните поле свойства **NameColumn** , а затем нажмите кнопку обзора (**...**), чтобы открыть диалоговое окно **Столбец имени** .</span><span class="sxs-lookup"><span data-stu-id="b465a-144">In the Properties window, click in the **NameColumn** property field and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>

11. <span data-ttu-id="b465a-145">В списке **Исходный столбец** выберите **EnglishProductCategoryName** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b465a-145">Select **EnglishProductCategoryName** in the **Source column** list and then click **OK**.</span></span>

12. <span data-ttu-id="b465a-146">На панели **Представление источника данных** найдите таблицу **DimProductSubcategory** , щелкните в ней правой кнопкой мыши столбец **ProductSubcategoryKey** и выберите команду **Создать атрибут из столбца**.</span><span class="sxs-lookup"><span data-stu-id="b465a-146">In the **Data Source View** pane, locate the **DimProductSubcategory** table, right-click **ProductSubcategoryKey** in that table, and then click **New Attribute from Column**.</span></span>

13. <span data-ttu-id="b465a-147">На панели **атрибуты** измените имя этого нового атрибута на `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="b465a-147">In the **Attributes** pane, change the name of this new attribute to `Subcategory`.</span></span>

14. <span data-ttu-id="b465a-148">В окно свойств щелкните поле свойства **NameColumn** , а затем нажмите кнопку обзора **(...)** , чтобы открыть диалоговое окно **Столбец имени** .</span><span class="sxs-lookup"><span data-stu-id="b465a-148">In the Properties window, click in the **NameColumn** property field and then click the browse **(...)** button to open the **Name Column** dialog box.</span></span>

15. <span data-ttu-id="b465a-149">В списке **Исходный столбец** выберите **EnglishProductSubcategoryName** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b465a-149">Select **EnglishProductSubcategoryName** in the **Source column** list and then click **OK**.</span></span>

16. <span data-ttu-id="b465a-150">Создайте новую пользовательскую иерархию с названием **категории продуктов** со следующими уровнями в порядке сверху вниз: `Category` , `Subcategory` и **Название продукта**.</span><span class="sxs-lookup"><span data-stu-id="b465a-150">Create a new user-defined hierarchy called **Product Categories** with the following levels, in order from top to bottom: `Category`, `Subcategory`, and **Product Name**.</span></span>

17. <span data-ttu-id="b465a-151">Укажите в `All Products` качестве значения свойства **AllMemberName** пользовательской иерархии категории продуктов.</span><span class="sxs-lookup"><span data-stu-id="b465a-151">Specify `All Products` as the value for the **AllMemberName** property of the Product Categories user-defined hierarchy.</span></span>

## <a name="browsing-the-user-defined-hierarchies-in-the-product-dimension"></a><span data-ttu-id="b465a-152">Просмотр пользовательских иерархий в измерении Product</span><span class="sxs-lookup"><span data-stu-id="b465a-152">Browsing the User-Defined Hierarchies in the Product Dimension</span></span>

1.  <span data-ttu-id="b465a-153">На панели инструментов вкладки **Структура измерения** в **конструкторе измерений** для измерения **Product** нажмите кнопку **Обработка**.</span><span class="sxs-lookup"><span data-stu-id="b465a-153">On the toolbar of the **Dimension Structure** tab of **Dimension Designer** for the **Product** dimension, click **Process**.</span></span>

2.  <span data-ttu-id="b465a-154">Нажмите кнопку **Да** , чтобы собрать и развернуть проект, а затем кнопку **Выполнить** , чтобы выполнить обработку измерения **Product** .</span><span class="sxs-lookup"><span data-stu-id="b465a-154">Click **Yes** to build and deploy the project, and then click **Run** to process the **Product** dimension.</span></span>

3.  <span data-ttu-id="b465a-155">По завершении обработки разверните узел **Обработка измерения "Product" завершена успешно** в диалоговом окне **Ход обработки** , разверните узел **Обработка атрибута измерения "Product Name" завершена**, а затем разверните узел **Запросы SQL 1**.</span><span class="sxs-lookup"><span data-stu-id="b465a-155">When processing has succeeded, expand **Processing Dimension 'Product' completed successfully** in the **Process Progress** dialog box, expand **Processing Dimension Attribute 'Product Name' completed**, and then expand **SQL queries 1**.</span></span>

4.  <span data-ttu-id="b465a-156">Щелкните запрос SELECT DISTINCT, а затем **Просмотр подробностей**.</span><span class="sxs-lookup"><span data-stu-id="b465a-156">Click the SELECT DISTINCT query and then click **View Details**.</span></span>

     <span data-ttu-id="b465a-157">Обратите внимание, что к предложению SELECT DISTINCT было добавлено предложение WHERE, удаляющее продукты, для которых не задано значение в столбце ProductSubcategoryKey, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="b465a-157">Notice that a WHERE clause has been added to the SELECT DISTINCT clause that removes those products that have no value in the ProductSubcategoryKey column, as shown in the following image.</span></span>

     <span data-ttu-id="b465a-158">![Предложение SELECT DISTINCT, показывающее предложение WHERE](../../2014/tutorials/media/l4-productnametraceline-1.gif "Предложение SELECT DISTINCT, показывающее предложение WHERE")</span><span class="sxs-lookup"><span data-stu-id="b465a-158">![SELECT DISTINCT clause showing WHERE clause](../../2014/tutorials/media/l4-productnametraceline-1.gif "SELECT DISTINCT clause showing WHERE clause")</span></span>

5.  <span data-ttu-id="b465a-159">Три раза нажмите кнопку **Закрыть** , чтобы закрыть все диалоговые окна.</span><span class="sxs-lookup"><span data-stu-id="b465a-159">Click **Close** three times to close all processing dialog boxes.</span></span>

6.  <span data-ttu-id="b465a-160">Перейдите на вкладку **Браузер** конструктора измерений для измерения **Product** и нажмите кнопку **Повтор соединения**.</span><span class="sxs-lookup"><span data-stu-id="b465a-160">Click the **Browser** tab in Dimension Designer for the **Product** dimension, and then click **Reconnect**.</span></span>

7.  <span data-ttu-id="b465a-161">Убедитесь, что в списке **Иерархия** отображаются **линии модели продукта** , `All Products` а затем разверните узел **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="b465a-161">Verify that **Product Model Lines** appears in the **Hierarchy** list, expand `All Products`, and then expand **Components**.</span></span>

8.  <span data-ttu-id="b465a-162">В списке **Иерархия** выберите **категории продуктов** , разверните `All Products` , а затем — **компоненты**.</span><span class="sxs-lookup"><span data-stu-id="b465a-162">Select **Product Categories** in the **Hierarchy** list, expand `All Products`, and then expand **Components**.</span></span>

     <span data-ttu-id="b465a-163">Обратите внимание, что не отображается ни один из компонентов сборки.</span><span class="sxs-lookup"><span data-stu-id="b465a-163">Notice that none of the assembly components appear.</span></span>

 <span data-ttu-id="b465a-164">Чтобы изменить поведение, упомянутое в предыдущей задаче, необходимо включить свойство **UnknownMember** измерения Products, задать значение для свойства **UnknownMemberName** , установить свойство **NullProcessing** для `Subcategory` атрибутов и **имени модели** в **UnknownMember**, определить `Category` атрибут в качестве связанного атрибута `Subcategory` атрибута, а затем определить атрибут « **линейка продукта** » как связанный атрибут атрибута « **имя модели** ».</span><span class="sxs-lookup"><span data-stu-id="b465a-164">To modify the behavior mentioned in the previous task, you will enable the **UnknownMember** property of the Products dimension, set a value for the **UnknownMemberName** property, set the **NullProcessing** property for the `Subcategory` and **Model Name** attributes to **UnknownMember**, define the `Category` attribute as a related attribute of the `Subcategory` attribute, and then define the **Product Line** attribute as a related attribute of the **Model Name** attribute.</span></span> <span data-ttu-id="b465a-165">В результате выполнения этих действий службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] станут использовать значение имени неизвестного элемента для товаров, не имеющих значений в столбце **SubcategoryKey** , как будет показано в следующей задаче.</span><span class="sxs-lookup"><span data-stu-id="b465a-165">These steps will cause [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use the unknown member name value for each product that does not have a value for the **SubcategoryKey** column, as you will see in the following task.</span></span>

## <a name="enabling-the-unknown-member-defining-attribute-relationships-and-specifying-custom-processing-properties-for-nulls"></a><span data-ttu-id="b465a-166">Включение неизвестного элемента, определение связей атрибутов и указание свойств пользовательской обработки для значений NULL</span><span class="sxs-lookup"><span data-stu-id="b465a-166">Enabling the Unknown Member, Defining Attribute Relationships, and Specifying Custom Processing Properties for Nulls</span></span>

1.  <span data-ttu-id="b465a-167">В конструкторе измерений для измерения **Product** перейдите на вкладку **Структура измерения** , а затем на панели **Атрибуты** выберите атрибут **Product** .</span><span class="sxs-lookup"><span data-stu-id="b465a-167">Click the **Dimension Structure** tab in Dimension Designer for the **Product** dimension, and then select **Product** in the **Attributes** pane.</span></span>

2.  <span data-ttu-id="b465a-168">В окне **Свойства** измените свойство **UnknownMember** на **Visible**, а затем измените значение свойства **UnknownMemberName** на `Assembly Components` .</span><span class="sxs-lookup"><span data-stu-id="b465a-168">In the **Properties** window, change the **UnknownMember** property to **Visible**, and then change the value for the **UnknownMemberName** property to `Assembly Components`.</span></span>

     <span data-ttu-id="b465a-169">Смена значения свойства **UnknownMember** на **Видимый** или **Скрытый** включит свойство **UnknownMember** для этого измерения.</span><span class="sxs-lookup"><span data-stu-id="b465a-169">Changing the **UnknownMember** property to either **Visible** or **Hidden** enables the **UnknownMember** property for the dimension.</span></span>

3.  <span data-ttu-id="b465a-170">Перейдите на вкладку **Связи атрибутов** .</span><span class="sxs-lookup"><span data-stu-id="b465a-170">Click the **Attribute Relationships** tab.</span></span>

4.  <span data-ttu-id="b465a-171">На диаграмме щелкните правой кнопкой мыши `Subcategory` атрибут и выберите пункт **создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="b465a-171">In the diagram, right-click the `Subcategory` attribute and then select **New Attribute Relationship**.</span></span>

5.  <span data-ttu-id="b465a-172">В диалоговом окне **Создание связи атрибутов** в поле **Исходный атрибут** имеет значение `Subcategory` .</span><span class="sxs-lookup"><span data-stu-id="b465a-172">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `Subcategory`.</span></span> <span data-ttu-id="b465a-173">Задайте для параметра **связанный атрибут** значение `Category` .</span><span class="sxs-lookup"><span data-stu-id="b465a-173">Set the **Related Attribute** to `Category`.</span></span> <span data-ttu-id="b465a-174">Оставьте для типа связи значение **Гибкая**.</span><span class="sxs-lookup"><span data-stu-id="b465a-174">Leave the relationship type set to **Flexible**.</span></span>

6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

7.  <span data-ttu-id="b465a-175">На панели **Атрибуты** выберите элемент **Subcategory**.</span><span class="sxs-lookup"><span data-stu-id="b465a-175">In the **Attributes** pane, select **Subcategory.**</span></span>

8.  <span data-ttu-id="b465a-176">В окне "Свойства" разверните свойство **KeyColumns** , а затем свойство **DimProductSubcategory.ProductSubcategoryKey (Integer)** .</span><span class="sxs-lookup"><span data-stu-id="b465a-176">In the Properties window, expand the **KeyColumns** property and then expand the **DimProductSubcategory.ProductSubcategoryKey (Integer)** property.</span></span>

9. <span data-ttu-id="b465a-177">Установите для свойства **NullProcessing** значение **UnknownMember**.</span><span class="sxs-lookup"><span data-stu-id="b465a-177">Change the **NullProcessing** property to **UnknownMember**.</span></span>

10. <span data-ttu-id="b465a-178">На панели **Атрибуты** выберите элемент **Model Name**.</span><span class="sxs-lookup"><span data-stu-id="b465a-178">In the **Attributes** pane, select **Model Name**.</span></span>

11. <span data-ttu-id="b465a-179">В окне "Свойства" разверните свойство **KeyColumns** , а затем свойство **Product.ModelName (WChar)** .</span><span class="sxs-lookup"><span data-stu-id="b465a-179">In the Properties window, expand the **KeyColumns** property and then expand the **Product.ModelName (WChar)** property.</span></span>

12. <span data-ttu-id="b465a-180">Установите для свойства **NullProcessing** значение **UnknownMember**.</span><span class="sxs-lookup"><span data-stu-id="b465a-180">Change the **NullProcessing** property to **UnknownMember**.</span></span>

     <span data-ttu-id="b465a-181">Из-за этих изменений при [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] обнаружении значения NULL для `Subcategory` атрибута или атрибута **имени модели** во время обработки значение неизвестного элемента будет заменено значением ключа, а пользовательские иерархии будут построены правильно.</span><span class="sxs-lookup"><span data-stu-id="b465a-181">Because of these changes, when [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] encounters a null value for the `Subcategory` attribute or the **Model Name** attribute during processing, the unknown member value will be substituted as the key value, and the user-defined hierarchies will be constructed correctly.</span></span>

## <a name="browsing-the-product-dimension-again"></a><span data-ttu-id="b465a-182">Повторный просмотр измерения Product</span><span class="sxs-lookup"><span data-stu-id="b465a-182">Browsing the Product Dimension Again</span></span>

1.  <span data-ttu-id="b465a-183">В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="b465a-183">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="b465a-184">После успешного развертывания перейдите на вкладку **Браузер** в конструкторе измерений для измерения **Product** и нажмите кнопку **Повтор соединения**.</span><span class="sxs-lookup"><span data-stu-id="b465a-184">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the **Product** dimension, and then click **Reconnect**.</span></span>

3.  <span data-ttu-id="b465a-185">Убедитесь, что в списке **Иерархия** выбраны **категории продуктов** , а затем разверните `All Products` .</span><span class="sxs-lookup"><span data-stu-id="b465a-185">Verify that **Product Categories** is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>

     <span data-ttu-id="b465a-186">Обратите внимание, что элемент Assembly Components отображается в качестве нового элемента на уровне категории.</span><span class="sxs-lookup"><span data-stu-id="b465a-186">Notice that Assembly Components appears as a new member of the Category level.</span></span>

4.  <span data-ttu-id="b465a-187">Разверните `Assembly Components` элемент `Category` уровня, а затем разверните `Assembly Components` элемент `Subcategory` уровня.</span><span class="sxs-lookup"><span data-stu-id="b465a-187">Expand the `Assembly Components` member of the `Category` level and then expand the `Assembly Components` member of the `Subcategory` level.</span></span>

     <span data-ttu-id="b465a-188">Обратите внимание, что все компоненты сборки отображаются на уровне **Product Name** , как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="b465a-188">Notice that all the assembly components now appear at the **Product Name** level, as shown in the following image.</span></span>

     <span data-ttu-id="b465a-189">![Уровень «Название продукта» с компонентами сборки](../../2014/tutorials/media/l4-assemblycomponents-1.gif "Уровень «Название продукта» с компонентами сборки")</span><span class="sxs-lookup"><span data-stu-id="b465a-189">![Product Name level showing assembly components](../../2014/tutorials/media/l4-assemblycomponents-1.gif "Product Name level showing assembly components")</span></span>

## <a name="next-lesson"></a><span data-ttu-id="b465a-190">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="b465a-190">Next Lesson</span></span>
 [<span data-ttu-id="b465a-191">Занятие 5.: Определение связей между измерениями и группами мер</span><span class="sxs-lookup"><span data-stu-id="b465a-191">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)


