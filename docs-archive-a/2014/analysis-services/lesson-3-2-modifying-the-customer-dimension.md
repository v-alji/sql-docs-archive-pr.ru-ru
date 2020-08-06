---
title: Изменение измерения «Заказчик» | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5b5aed99-1760-4bc7-b248-52ecb0b97ebc
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd5c5c47205a89f8429b0b6f0ba55da266d5e811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666253"
---
# <a name="modifying-the-customer-dimension"></a><span data-ttu-id="c6dfc-102">Изменение измерения «Заказчик»</span><span class="sxs-lookup"><span data-stu-id="c6dfc-102">Modifying the Customer Dimension</span></span>
  <span data-ttu-id="c6dfc-103">Существует много способов повысить удобство использования и функциональность измерений куба.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-103">There are many different ways that you can increase the usability and functionality of the dimensions in a cube.</span></span> <span data-ttu-id="c6dfc-104">При выполнении задач этого раздела будет изменено измерение «Заказчик».</span><span class="sxs-lookup"><span data-stu-id="c6dfc-104">In the tasks in this topic, you modify the Customer dimension.</span></span>  
  
## <a name="renaming-attributes"></a><span data-ttu-id="c6dfc-105">Переименование атрибутов</span><span class="sxs-lookup"><span data-stu-id="c6dfc-105">Renaming Attributes</span></span>  
 <span data-ttu-id="c6dfc-106">Имена атрибутов можно изменить на вкладке **Структура измерения** конструктора измерений.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-106">You can change attribute names with the **Dimension Structure** tab of Dimension Designer.</span></span>  
  
#### <a name="to-rename-an-attribute"></a><span data-ttu-id="c6dfc-107">Переименование атрибута</span><span class="sxs-lookup"><span data-stu-id="c6dfc-107">To rename an attribute</span></span>  
  
1.  <span data-ttu-id="c6dfc-108">Откройте измерение "Заказчик" в **конструкторе измерений** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6dfc-108">Switch to **Dimension Designer** for the Customer dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c6dfc-109">Для этого дважды щелкните измерение **Заказчик** в узле **Измерения** обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-109">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="c6dfc-110">На панели **Атрибуты** щелкните правой кнопкой мыши атрибут **English Country Region Name**и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-110">In the **Attributes** pane, right-click **English Country Region Name**, and then click **Rename**.</span></span> <span data-ttu-id="c6dfc-111">Измените имя атрибута на `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-111">Change the name of the attribute to `Country-Region`.</span></span>  
  
3.  <span data-ttu-id="c6dfc-112">Аналогичным образом измените имена следующих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-112">Change the names of the following attributes in the same manner:</span></span>  
  
    -   <span data-ttu-id="c6dfc-113">**Английский атрибут образования** — изменение на`Education`</span><span class="sxs-lookup"><span data-stu-id="c6dfc-113">**English Education** attribute - change to `Education`</span></span>  
  
    -   <span data-ttu-id="c6dfc-114">**Английский** атрибут "род" — изменение на`Occupation`</span><span class="sxs-lookup"><span data-stu-id="c6dfc-114">**English Occupation** attribute - change to `Occupation`</span></span>  
  
    -   <span data-ttu-id="c6dfc-115">**Имя района штата** — изменить на`State-Province`</span><span class="sxs-lookup"><span data-stu-id="c6dfc-115">**State Province Name** attribute - change to `State-Province`</span></span>  
  
4.  <span data-ttu-id="c6dfc-116">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="c6dfc-117">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="c6dfc-117">Creating a Hierarchy</span></span>  
 <span data-ttu-id="c6dfc-118">Иерархию можно создать, перетащив атрибут с панели **Атрибуты** на панель **Иерархии** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-118">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="c6dfc-119">Создание иерархии</span><span class="sxs-lookup"><span data-stu-id="c6dfc-119">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="c6dfc-120">Перетащите `Country-Region` атрибут с панели **атрибуты** на панель **иерархии** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-120">Drag the `Country-Region` attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="c6dfc-121">Перетащите `State-Province` атрибут из панели **атрибуты** в **\<new level>** ячейку на панели **иерархии** под `Country-Region` уровнем.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-121">Drag the `State-Province` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `Country-Region` level.</span></span>  
  
3.  <span data-ttu-id="c6dfc-122">Перетащите атрибут **City** с панели **атрибуты** в **\<new level>** ячейку на панели **иерархии** под `State-Province` уровнем.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-122">Drag the **City** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `State-Province` level.</span></span>  
  
4.  <span data-ttu-id="c6dfc-123">На панели **иерархии** вкладки **Структура измерения** щелкните правой кнопкой мыши строку заголовка иерархии **Иерархия** , выберите команду **Переименовать**, а затем введите `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-123">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, select **Rename**, and then type `Customer Geography`.</span></span>  
  
     <span data-ttu-id="c6dfc-124">Теперь имя иерархии — `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-124">The name of the hierarchy is now `Customer Geography`.</span></span>  
  
5.  <span data-ttu-id="c6dfc-125">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-125">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="c6dfc-126">Добавление именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="c6dfc-126">Adding a Named Calculation</span></span>  
 <span data-ttu-id="c6dfc-127">К таблице в представлении источника данных можно добавить именованное вычисление, которое является выражением SQL и представляет собой вычисляемый столбец,</span><span class="sxs-lookup"><span data-stu-id="c6dfc-127">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="c6dfc-128">Это выражение имеет вид и функции столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-128">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="c6dfc-129">Именованные вычисления позволяют расширять реляционную схему таблиц, существующих в представлении источника данных, не изменяя структуру таблиц в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-129">Named calculations let you extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="c6dfc-130">Дополнительные сведения см. в разделе [Определение именованных вычислений в представлении источника данных (службы Analysis Services)](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="c6dfc-130">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="c6dfc-131">Добавление именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="c6dfc-131">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="c6dfc-132">Откройте представление источника данных \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* , дважды щелкнув его в папке **представления источников данных** в Обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-132">Open the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view by double-clicking it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="c6dfc-133">На панели **Таблицы** слева щелкните правой кнопкой мыши таблицу **Заказчик**и выберите команду **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-133">In the **Tables** pane on the left, right-click **Customer**, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="c6dfc-134">В диалоговом окне **Создание именованного вычисления** введите `FullName` в поле **имя столбца** , а затем в поле Выражение введите или скопируйте и вставьте следующую `CASE` инструкцию **Expression** :</span><span class="sxs-lookup"><span data-stu-id="c6dfc-134">In the **Create Named Calculation** dialog box, type `FullName` in the **Column name** box, and then type or copy and paste the following `CASE` statement in the **Expression** box:</span></span>  
  
    ```  
    CASE  
       WHEN MiddleName IS NULL THEN  
       FirstName + ' ' + LastName  
       ELSE  
       FirstName + ' ' + MiddleName + ' ' + LastName  
    END  
    ```  
  
     <span data-ttu-id="c6dfc-135">`CASE`Инструкция объединяет столбцы **FirstName**, **MiddleName**и **LastName** в один столбец, который будет использоваться в измерении Customer в качестве отображаемого имени для атрибута **Customer** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-135">The `CASE` statement concatenates the **FirstName**, **MiddleName**, and **LastName** columns into a single column that you will use in the Customer dimension as the displayed name for the **Customer** attribute.</span></span>  
  
4.  <span data-ttu-id="c6dfc-136">Нажмите кнопку **ОК**, а затем разверните узел **Заказчик** на панели **Таблицы** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-136">Click **OK**, and then expand **Customer** in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="c6dfc-137">`FullName`Именованное вычисление отображается в списке столбцов в таблице Customer со значком, указывающим на то, что это именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-137">The `FullName` named calculation appears in the list of columns in the Customer table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="c6dfc-138">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-138">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="c6dfc-139">На панели **Таблицы** щелкните правой кнопкой мыши таблицу **Заказчик**и выберите пункт **Просмотр данных**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-139">In the **Tables** pane, right-click **Customer**, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="c6dfc-140">Просмотрите последний столбец в представлении **Просмотр таблицы "Заказчик"** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-140">Review the last column in the **Explore Customer Table** view.</span></span>  
  
     <span data-ttu-id="c6dfc-141">Обратите внимание, что `FullName` столбец отображается в представлении источника данных, правильно объединяя данные из нескольких столбцов базового источника данных и не изменяя исходный источник данных.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-141">Notice that the `FullName` column appears in the data source view, correctly concatenating data from several columns from the underlying data source and without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="c6dfc-142">Закройте вкладку **Просмотр таблицы Customer** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-142">Close the **Explore Customer Table** tab.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="c6dfc-143">Использование именованных вычислений в качестве имен элементов</span><span class="sxs-lookup"><span data-stu-id="c6dfc-143">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="c6dfc-144">После создания именованного вычисления в представлении источника данных это вычисление можно использовать в качестве свойства атрибута.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-144">After you have created a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="c6dfc-145">Использование именованного вычисления в качестве имен элементов</span><span class="sxs-lookup"><span data-stu-id="c6dfc-145">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="c6dfc-146">В конструкторе измерений откройте измерение Customer.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-146">Switch to Dimension Designer for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="c6dfc-147">На панели **Атрибуты** вкладки **Структура измерения** выберите атрибут **Customer Key** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-147">In the **Attributes** pane of the **Dimension Structure** tab, click the **Customer Key** attribute.</span></span>  
  
3.  <span data-ttu-id="c6dfc-148">Откройте окно "Свойства" и нажмите в строке заголовка кнопку **Автоматически скрывать** , чтобы оно оставалось открытым.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-148">Open the Properties window and click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="c6dfc-149">В поле **имя** свойства введите `Full Name` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-149">In the **Name** property field, type `Full Name`.</span></span>  
  
5.  <span data-ttu-id="c6dfc-150">Щелкните в нижней части поля свойства **NameColumn** , а затем нажмите кнопку обзора (**...**), чтобы открыть диалоговое окно **Столбец имени** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-150">Click in the **NameColumn** property field at the bottom, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
6.  <span data-ttu-id="c6dfc-151">Выберите `FullName` в нижней части списка **Исходный столбец** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-151">Select `FullName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="c6dfc-152">На вкладке Структура измерений перетащите `Full Name` атрибут из панели **атрибуты** в **\<new level>** ячейку на панели **иерархии** под уровнем **City** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-152">In the Dimensions Structure tab, drag the `Full Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **City** level.</span></span>  
  
8.  <span data-ttu-id="c6dfc-153">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-153">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-display-folders"></a><span data-ttu-id="c6dfc-154">Определение папок отображения</span><span class="sxs-lookup"><span data-stu-id="c6dfc-154">Defining Display Folders</span></span>  
 <span data-ttu-id="c6dfc-155">Папки отображения позволяют группировать пользовательские иерархии и иерархии атрибутов в структуры папок, удобные для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-155">You can use display folders to group user and attribute hierarchies into folder structures to increase usability.</span></span>  
  
#### <a name="to-define-display-folders"></a><span data-ttu-id="c6dfc-156">Определение папок отображения</span><span class="sxs-lookup"><span data-stu-id="c6dfc-156">To define display folders</span></span>  
  
1.  <span data-ttu-id="c6dfc-157">Откройте вкладку **Структура измерения** для измерения "Заказчик".</span><span class="sxs-lookup"><span data-stu-id="c6dfc-157">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="c6dfc-158">На панели **Атрибуты** выберите следующие атрибуты (щелкните каждый из них, удерживая нажатой клавишу CTRL):</span><span class="sxs-lookup"><span data-stu-id="c6dfc-158">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="c6dfc-159">**Город**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-159">**City**</span></span>  
  
    -   `Country-Region`  
  
    -   <span data-ttu-id="c6dfc-160">**Почтовый индекс**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-160">**Postal Code**</span></span>  
  
    -   `State-Province`  
  
3.  <span data-ttu-id="c6dfc-161">В окно свойств щелкните поле свойства **AttributeHierarchyDisplayFolder** в верхней части страницы (может потребоваться указать его, чтобы увидеть полное имя), а затем введите `Location` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-161">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top (you might need to point to it to see the full name), and then type `Location`.</span></span>  
  
4.  <span data-ttu-id="c6dfc-162">На панели **иерархии** щелкните `Customer Geography` , а затем в окно свойств справа выберите в `Location` качестве значения свойства **DisplayFolder** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-162">In the **Hierarchies** pane, click `Customer Geography`, and then in the Properties window on the right, select `Location` as the value of the **DisplayFolder** property.</span></span>  
  
5.  <span data-ttu-id="c6dfc-163">На панели **Атрибуты** выберите следующие атрибуты (щелкните каждый из них, удерживая нажатой клавишу CTRL):</span><span class="sxs-lookup"><span data-stu-id="c6dfc-163">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="c6dfc-164">**Расстояние до работы**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-164">**Commute Distance**</span></span>  
  
    -   `Education`  
  
    -   <span data-ttu-id="c6dfc-165">**Gender**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-165">**Gender**</span></span>  
  
    -   <span data-ttu-id="c6dfc-166">**House Owner Flag**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-166">**House Owner Flag**</span></span>  
  
    -   <span data-ttu-id="c6dfc-167">**Семейное положение**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-167">**Marital Status**</span></span>  
  
    -   <span data-ttu-id="c6dfc-168">**Number Cars Owned**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-168">**Number Cars Owned**</span></span>  
  
    -   <span data-ttu-id="c6dfc-169">**Число детей в домашней сети**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-169">**Number Children At Home**</span></span>  
  
    -   `Occupation`  
  
    -   <span data-ttu-id="c6dfc-170">**Общее количество детей**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-170">**Total Children**</span></span>  
  
    -   <span data-ttu-id="c6dfc-171">**Годовой доход**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-171">**Yearly Income**</span></span>  
  
6.  <span data-ttu-id="c6dfc-172">В окно свойств щелкните поле свойства **AttributeHierarchyDisplayFolder** в верхней части, а затем введите `Demographic` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-172">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top, and then type `Demographic`.</span></span>  
  
7.  <span data-ttu-id="c6dfc-173">На панели **Атрибуты** выберите следующие атрибуты (щелкните каждый из них, удерживая нажатой клавишу CTRL):</span><span class="sxs-lookup"><span data-stu-id="c6dfc-173">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="c6dfc-174">**Электронная почта**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-174">**Email Address**</span></span>  
  
    -   <span data-ttu-id="c6dfc-175">**Факс**</span><span class="sxs-lookup"><span data-stu-id="c6dfc-175">**Phone**</span></span>  
  
8.  <span data-ttu-id="c6dfc-176">В окно свойств щелкните поле свойства **AttributeHierarchyDisplayFolder** и введите `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-176">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field and type `Contacts`.</span></span>  
  
9. <span data-ttu-id="c6dfc-177">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-177">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns"></a><span data-ttu-id="c6dfc-178">Определение составных ключевых столбцов</span><span class="sxs-lookup"><span data-stu-id="c6dfc-178">Defining Composite KeyColumns</span></span>  
 <span data-ttu-id="c6dfc-179">Свойство **KeyColumns** содержит столбец или столбцы, представляющие ключ для атрибута.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-179">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="c6dfc-180">На этом занятии вы создадите составной ключ для **города** и `State-Province` атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-180">In this lesson, you create a composite key for the **City** and `State-Province` attributes.</span></span> <span data-ttu-id="c6dfc-181">Составные ключи могут оказаться полезными для уникальной идентификации атрибута.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-181">Composite keys can be helpful when you need to uniquely identify an attribute.</span></span> <span data-ttu-id="c6dfc-182">Например, при определении связей атрибутов далее в этом руководстве атрибут **City** должен однозначно идентифицировать `State-Province` атрибут.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-182">For example, when you define attribute relationships later in this tutorial, a **City** attribute must uniquely identify a `State-Province` attribute.</span></span> <span data-ttu-id="c6dfc-183">Однако в разных областях бывают города с одинаковыми названиями.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-183">However, there could be several cities with the same name in different states.</span></span> <span data-ttu-id="c6dfc-184">Поэтому для атрибута **City** необходимо создать составной ключ, состоящий из столбцов **StateProvinceName** и **City** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-184">For this reason, you will create a composite key that is composed of the **StateProvinceName** and **City** columns for the **City** attribute.</span></span> <span data-ttu-id="c6dfc-185">Дополнительные сведения см. в разделе [Изменение свойства KeyColumn атрибута](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-185">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-city-attribute"></a><span data-ttu-id="c6dfc-186">Определение составного свойства KeyColumns для атрибута City</span><span class="sxs-lookup"><span data-stu-id="c6dfc-186">To define composite KeyColumns for the City attribute</span></span>  
  
1.  <span data-ttu-id="c6dfc-187">Откройте вкладку **Структура измерения** для измерения "Заказчик".</span><span class="sxs-lookup"><span data-stu-id="c6dfc-187">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="c6dfc-188">На панели **Атрибуты** щелкните атрибут **City** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-188">In the **Attributes** pane, click the **City** attribute.</span></span>  
  
3.  <span data-ttu-id="c6dfc-189">В окне **Свойства** щелкните в поле **KeyColumns** ближе к нижней части и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-189">In the **Properties** window, click in the **KeyColumns** field near the bottom, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="c6dfc-190">В диалоговом окне **Ключевые столбцы** в списке **Доступные столбцы** выберите столбец **StateProvinceName**и нажмите кнопку **>** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-190">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **StateProvinceName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="c6dfc-191">Теперь в списке **Ключевые столбцы** отображаются столбцы **City** и **StateProvinceName** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-191">The **City** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="c6dfc-192">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-192">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="c6dfc-193">Чтобы задать свойство **NameColumn** атрибута **City** , щелкните в окне свойств поле **NameColumn** и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-193">To set the **NameColumn** property of the **City** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="c6dfc-194">В диалоговом окне **Столбец имени** в списке **Исходный столбец** выберите **City**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-194">In the **Name Column** dialog box, in the **Source column** list, select **City**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="c6dfc-195">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-195">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-state-province-attribute"></a><span data-ttu-id="c6dfc-196">Определение составного свойства KeyColumns для атрибута «Республика, область или край»</span><span class="sxs-lookup"><span data-stu-id="c6dfc-196">To define composite KeyColumns for the State-Province attribute</span></span>  
  
1.  <span data-ttu-id="c6dfc-197">Убедитесь в том, что вкладка **Структура измерения** для измерения "Заказчик" открыта.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-197">Make sure the **Dimension Structure** tab for the Customer dimension is open.</span></span>  
  
2.  <span data-ttu-id="c6dfc-198">На панели **атрибуты** щелкните `State-Province` атрибут.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-198">In the **Attributes** pane, click the `State-Province` attribute.</span></span>  
  
3.  <span data-ttu-id="c6dfc-199">В окне **Свойства** щелкните в поле **KeyColumns** и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-199">In the **Properties** window, click in the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="c6dfc-200">В диалоговом окне **Ключевые столбцы** в списке **Доступные столбцы** выберите столбец **EnglishCountryRegionName**и нажмите кнопку **>** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-200">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **EnglishCountryRegionName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="c6dfc-201">Теперь в списке **Ключевые столбцы** отображаются столбцы **EnglishCountryRegionName** и **StateProvinceName** .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-201">The **EnglishCountryRegionName** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="c6dfc-202">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-202">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="c6dfc-203">Чтобы задать свойство **NameColumn** `State-Province` атрибута, щелкните поле **NameColumn** в окно свойств и нажмите кнопку обзора (**...**).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-203">To set the **NameColumn** property of the `State-Province` attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="c6dfc-204">В диалоговом окне **Столбец имени** в списке **Исходный столбец** выберите **StateProvinceName**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-204">In the **Name Column** dialog box, in the **Source column** list, select **StateProvinceName**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="c6dfc-205">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-205">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="c6dfc-206">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="c6dfc-206">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="c6dfc-207">Необходимо определять связи между атрибутами, если базовые данные это поддерживают.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-207">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="c6dfc-208">Определение связей между атрибутами ускоряет обработку измерений, секций и запросов.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-208">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="c6dfc-209">Дополнительные сведения см. в разделах [Определение связей атрибутов](multidimensional-models/attribute-relationships-define.md) и [Связи атрибутов](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-209">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="c6dfc-210">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="c6dfc-210">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="c6dfc-211">В **конструкторе измерений** для измерения «Заказчик» перейдите на вкладку **связи атрибутов** . Может потребоваться подождать.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-211">In the **Dimension Designer** for the Customer dimension, click the **Attribute Relationships** tab. You might need to wait.</span></span>  
  
2.  <span data-ttu-id="c6dfc-212">На диаграмме щелкните правой кнопкой мыши атрибут **Город** и выберите команду **Создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-212">In the diagram, right-click the **City** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="c6dfc-213">В диалоговом окне **Создание связи атрибутов** поле **Исходный атрибут** содержит значение **Город**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-213">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **City**.</span></span> <span data-ttu-id="c6dfc-214">Задайте для параметра **связанный атрибут** значение `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-214">Set the **Related Attribute** to `State-Province`.</span></span>  
  
4.  <span data-ttu-id="c6dfc-215">В списке **Тип связи** выберите тип **Жесткая**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-215">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="c6dfc-216">Связь имеет тип **Жесткая** , так как связи между элементами не будут меняться с течением времени.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-216">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span> <span data-ttu-id="c6dfc-217">Например, переход города под юрисдикцию другого штата или провинции — явление крайне редкое.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-217">For example, it would be unusual for a city to become part of a different state or province.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c6dfc-218">На диаграмме щелкните правой кнопкой мыши `State-Province` атрибут и выберите пункт **создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-218">In the diagram, right-click the `State-Province` attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="c6dfc-219">В диалоговом окне **Создание связи атрибутов** в поле **Исходный атрибут** имеет значение `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-219">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `State-Province`.</span></span> <span data-ttu-id="c6dfc-220">Задайте для параметра **связанный атрибут** значение `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-220">Set the **Related Attribute** to `Country-Region`.</span></span>  
  
8.  <span data-ttu-id="c6dfc-221">В списке **Тип связи** выберите тип **Жесткая**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-221">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="c6dfc-222">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-222">Click **OK**.</span></span>  
  
10. <span data-ttu-id="c6dfc-223">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-223">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-changes-processing-the-objects-and-viewing-the-changes"></a><span data-ttu-id="c6dfc-224">Развертывание изменений, обработка объектов и просмотр изменений</span><span class="sxs-lookup"><span data-stu-id="c6dfc-224">Deploying Changes, Processing the Objects, and Viewing the Changes</span></span>  
 <span data-ttu-id="c6dfc-225">После изменения атрибутов и иерархий необходимо произвести развертывание произведенных изменений и повторную обработку связанных объектов, прежде чем эти изменения можно будет просмотреть.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-225">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-the-changes-process-the-objects-and-view-the-changes"></a><span data-ttu-id="c6dfc-226">Развертывание изменений, обработка объектов и просмотр изменений</span><span class="sxs-lookup"><span data-stu-id="c6dfc-226">To deploy the changes, process the objects, and view the changes</span></span>  
  
1.  <span data-ttu-id="c6dfc-227">В меню **Построение** среды [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-227">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="c6dfc-228">Получив сообщение **Развертывание выполнено успешно** , в конструкторе измерений перейдите на вкладку **Браузер** измерения "Заказчик" и щелкните на панели инструментов значок повторного соединения.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-228">After you receive the **Deployment Completed Successfully** message, click the **Browser** tab of Dimension Designer for the Customer dimension, and then click the Reconnect button on the left side of the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="c6dfc-229">Убедитесь, что `Customer Geography` в списке **Иерархия** выбрано значение, а затем в области браузер разверните **все**, разверните **Австралия**, разверните узел **Новый Южный**, а затем разверните узел **Коффс Харбор**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-229">Verify that `Customer Geography` is selected in the **Hierarchy** list, and then in the browser pane, expand **All**, expand **Australia**, expand **New South Wales**, and then expand **Coffs Harbour**.</span></span>  
  
     <span data-ttu-id="c6dfc-230">В браузере отображаются заказчики, живущие в этом городе.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-230">The browser displays the customers in the city.</span></span>  
  
4.  <span data-ttu-id="c6dfc-231">Переключитесь в **конструктор кубов** для куба учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6dfc-231">Switch to **Cube Designer** for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="c6dfc-232">Чтобы сделать это, дважды щелкните куб **Учебник по службам Analysis Services** , который находится в узле **Кубы** в дереве **обозревателя решений**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-232">To do this, double-click the **Analysis Services Tutorial** cube in the **Cubes** node of **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="c6dfc-233">Перейдите на вкладку **Браузер** и на панели инструментов конструктора нажмите кнопку повторного соединения.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-233">Click the **Browser** tab, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
6.  <span data-ttu-id="c6dfc-234">На панели **Группа мер** разверните узел **Заказчик**.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-234">In the **Measure Group** pane, expand **Customer**.</span></span>  
  
     <span data-ttu-id="c6dfc-235">Обратите внимание, что вместо длинного списка атрибутов для измерения «Заказчик» отображаются только папки отображения и те атрибуты, для которых не указана папка отображения.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-235">Notice that instead of a long list of attributes, only the display folders and the attributes that do not have display folder values appear underneath Customer.</span></span>  
  
7.  <span data-ttu-id="c6dfc-236">В меню **File** (Файл) выберите команду **Save All** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-236">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c6dfc-237">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="c6dfc-237">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c6dfc-238">Изменение измерения Product</span><span class="sxs-lookup"><span data-stu-id="c6dfc-238">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="c6dfc-239">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6dfc-239">See Also</span></span>  
 <span data-ttu-id="c6dfc-240">[Справочник по свойствам атрибутов измерения](multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c6dfc-240">[Dimension Attribute Properties Reference](multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="c6dfc-241">[Удаление атрибута из измерения](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="c6dfc-241">[Remove an Attribute from a Dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span></span>  
 <span data-ttu-id="c6dfc-242">[Переименование атрибута](multidimensional-models/attribute-properties-rename-an-attribute.md) </span><span class="sxs-lookup"><span data-stu-id="c6dfc-242">[Rename an Attribute](multidimensional-models/attribute-properties-rename-an-attribute.md) </span></span>  
 [<span data-ttu-id="c6dfc-243">Определение именованных вычислений в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="c6dfc-243">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
