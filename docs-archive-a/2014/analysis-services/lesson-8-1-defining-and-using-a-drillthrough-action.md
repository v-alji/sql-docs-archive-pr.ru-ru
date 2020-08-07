---
title: Определение и использование действия детализации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3765f865-2b93-44be-b290-28e3815d5ecb
author: minewiskan
ms.author: owend
ms.openlocfilehash: ea19a9721d87936bc88b5401c71ee550a47bc1ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731025"
---
# <a name="defining-and-using-a-drillthrough-action"></a><span data-ttu-id="330b1-102">Определение и использование действия детализации</span><span class="sxs-lookup"><span data-stu-id="330b1-102">Defining and Using a Drillthrough Action</span></span>
  <span data-ttu-id="330b1-103">Распределение данных фактов по измерениям фактов без верной фильтрации данных, возвращаемых запросом, может привести к снижению его производительности.</span><span class="sxs-lookup"><span data-stu-id="330b1-103">Dimensioning fact data by a fact dimension without correctly filtering the data that the query returns can cause slow query performance.</span></span> <span data-ttu-id="330b1-104">Чтобы избежать этого, можно определить действие детализации, которое ограничит общее число возвращаемых строк.</span><span class="sxs-lookup"><span data-stu-id="330b1-104">To avoid this, you can define a drillthrough action that restricts the total number of rows that are returned.</span></span> <span data-ttu-id="330b1-105">Это позволит значительно повысить производительность выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="330b1-105">This will significantly improve query performance.</span></span>  
  
 <span data-ttu-id="330b1-106">В задачах этого раздела предстоит создать действие детализации, возвращающее пользователям через Интернет подробные сведения о заказе на продажу.</span><span class="sxs-lookup"><span data-stu-id="330b1-106">In the tasks in this topic, you define a drillthrough action to return order detail information for sales to customers over the Internet.</span></span>  
  
## <a name="defining-the-drillthrough-action-properties"></a><span data-ttu-id="330b1-107">Определение свойств действия детализации</span><span class="sxs-lookup"><span data-stu-id="330b1-107">Defining the Drillthrough Action Properties</span></span>  
  
1.  <span data-ttu-id="330b1-108">Откройте куб "Учебник по [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] " в конструкторе кубов и перейдите на вкладку **Действия** .</span><span class="sxs-lookup"><span data-stu-id="330b1-108">In Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, click the **Actions** tab.</span></span>  
  
     <span data-ttu-id="330b1-109">Вкладка **Действия** содержит несколько панелей.</span><span class="sxs-lookup"><span data-stu-id="330b1-109">The **Actions** tab includes several panes.</span></span> <span data-ttu-id="330b1-110">В левой части вкладки находятся панели **Организатор действий** и **Средства вычисления** .</span><span class="sxs-lookup"><span data-stu-id="330b1-110">On the left side of the tab are the **Action Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="330b1-111">Справа от них находится панель **Отображение** , содержащая подробные сведения о действии, выбранном на панели **Организатор действий** .</span><span class="sxs-lookup"><span data-stu-id="330b1-111">The pane to the right of these two panes is the **Display** pane, which contains the details of the action that is selected in the **Action Organizer** pane.</span></span>  
  
     <span data-ttu-id="330b1-112">На рисунке ниже показана вкладка **Действия** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="330b1-112">The following image shows the **Actions** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="330b1-113">![Вкладка «Действия» конструктора кубов](../../2014/tutorials/media/l8-action1.gif "Вкладка «Действия» конструктора кубов")</span><span class="sxs-lookup"><span data-stu-id="330b1-113">![Actions tab of Cube Designer](../../2014/tutorials/media/l8-action1.gif "Actions tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="330b1-114">На панели инструментов вкладки **Действия** нажмите кнопку **Создать действие детализации** .</span><span class="sxs-lookup"><span data-stu-id="330b1-114">On the toolbar of the **Actions** tab, click the **New Drillthrough Action** button.</span></span>  
  
     <span data-ttu-id="330b1-115">В панели отображения появится пустой шаблон действия.</span><span class="sxs-lookup"><span data-stu-id="330b1-115">A blank action template appears in the display pane.</span></span>  
  
     <span data-ttu-id="330b1-116">![Пустой шаблон действия на панели отображения](../../2014/tutorials/media/l8-action2.gif "Пустой шаблон действия на панели отображения")</span><span class="sxs-lookup"><span data-stu-id="330b1-116">![Blank Action template in the display pane](../../2014/tutorials/media/l8-action2.gif "Blank Action template in the display pane")</span></span>  
  
3.  <span data-ttu-id="330b1-117">В поле **имя** измените имя этого действия на `Internet Sales Details Drillthrough Action` .</span><span class="sxs-lookup"><span data-stu-id="330b1-117">In the **Name** box, change the name of this action to `Internet Sales Details Drillthrough Action`.</span></span>  
  
4.  <span data-ttu-id="330b1-118">В списке **Элементы группы мер** выберите значение **Продажи через Интернет**.</span><span class="sxs-lookup"><span data-stu-id="330b1-118">In the **Measure group members** list, select **Internet Sales**.</span></span>  
  
5.  <span data-ttu-id="330b1-119">В поле **Столбцы детализации** выберите в списке **Измерения** значение **Подробности заказа через Интернет** .</span><span class="sxs-lookup"><span data-stu-id="330b1-119">In the **Drillthrough Columns** box, select **Internet Sales Order Details** in the **Dimensions** list.</span></span>  
  
6.  <span data-ttu-id="330b1-120">В списке **Возвращаемые столбцы** установите флажки **Описание элемента** и **Номер заказа** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="330b1-120">In the **Return Columns** list, select the **Item Description** and the **Order Number** check boxes, and then click **OK**.</span></span> <span data-ttu-id="330b1-121">На следующем рисунке показано, как выглядит шаблон действия в этот момент времени данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="330b1-121">The following image shows the Action template as it should appear at this point in this procedure.</span></span>  
  
     <span data-ttu-id="330b1-122">![Поле «Столбцы детализации»](../../2014/tutorials/media/l8-action3.gif "Поле «Столбцы детализации»")</span><span class="sxs-lookup"><span data-stu-id="330b1-122">![Drillthrough Columns box](../../2014/tutorials/media/l8-action3.gif "Drillthrough Columns box")</span></span>  
  
7.  <span data-ttu-id="330b1-123">Разверните поле **Дополнительные свойства** , как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="330b1-123">Expand the **Additional Properties** box, as shown in the following image.</span></span>  
  
     <span data-ttu-id="330b1-124">![Поле «Дополнительные свойства»](../../2014/tutorials/media/l8-action4.gif "Поле «Дополнительные свойства»")</span><span class="sxs-lookup"><span data-stu-id="330b1-124">![Additional Properties box](../../2014/tutorials/media/l8-action4.gif "Additional Properties box")</span></span>  
  
8.  <span data-ttu-id="330b1-125">В поле **Максимальное число строк** введите `10` .</span><span class="sxs-lookup"><span data-stu-id="330b1-125">In the **Maximum Rows** box, type `10`.</span></span>  
  
9. <span data-ttu-id="330b1-126">В поле **заголовок** введите `Drillthrough to Order Details...` .</span><span class="sxs-lookup"><span data-stu-id="330b1-126">In the **Caption** box, type `Drillthrough to Order Details...`.</span></span>  
  
     <span data-ttu-id="330b1-127">Эти настройки ограничивают количество возвращаемых строк и указывают заголовок, отображаемый в меню клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="330b1-127">These settings limit the number of rows returned and specify the caption that appears in the client application menu.</span></span> <span data-ttu-id="330b1-128">На рисунке ниже показаны эти параметры в поле **Дополнительные свойства** .</span><span class="sxs-lookup"><span data-stu-id="330b1-128">The following image shows these settings in the **AdditionalProperties** box.</span></span>  
  
     <span data-ttu-id="330b1-129">![Поле «Дополнительные свойства»](../../2014/tutorials/media/l8-action5.gif "Поле «Дополнительные свойства»")</span><span class="sxs-lookup"><span data-stu-id="330b1-129">![Additional Properties box](../../2014/tutorials/media/l8-action5.gif "Additional Properties box")</span></span>  
  
## <a name="using-the-drillthrough-action"></a><span data-ttu-id="330b1-130">Использование действия детализации</span><span class="sxs-lookup"><span data-stu-id="330b1-130">Using the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="330b1-131">В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="330b1-131">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="330b1-132">После успешного завершения развертывания в конструкторе кубов, где открыт куб **Tutorial, перейдите на вкладку** Браузер [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и нажмите кнопку **Повторное соединение** .</span><span class="sxs-lookup"><span data-stu-id="330b1-132">When deployment has successfully completed, click the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="330b1-133">Запустите Excel.</span><span class="sxs-lookup"><span data-stu-id="330b1-133">Start Excel.</span></span>  
  
4.  <span data-ttu-id="330b1-134">Добавьте меру **Продажи через Интернет — объем продаж** в область значений.</span><span class="sxs-lookup"><span data-stu-id="330b1-134">Add the **Internet Sales-Sales Amount** measure to the Values area.</span></span>  
  
5.  <span data-ttu-id="330b1-135">Добавьте определенную пользователем иерархию **География заказчика** из папки **Расположение** в измерении **Заказчик** в область **Фильтр отчета** .</span><span class="sxs-lookup"><span data-stu-id="330b1-135">Add the **Customer Geography** user-defined hierarchy from the **Location** folder in the **Customer** dimension to the **Report Filter** area.</span></span>  
  
6.  <span data-ttu-id="330b1-136">В сводной таблице в столбце **География заказчика**добавьте фильтр, который выбирает одного заказчика.</span><span class="sxs-lookup"><span data-stu-id="330b1-136">On the PivotTable, in **Customer Geography**, add a filter that selects a single customer.</span></span> <span data-ttu-id="330b1-137">Разверните узлы **Все заказчики**, **Австралия**, **Квинсленд**, **Брисбейн**, **4000**, установите флажок **Адам Пауэл**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="330b1-137">Expand **All Customers**, expand **Australia**, expand **Queensland**, expand **Brisbane**, expand **4000**, select the check box for **Adam Powell**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="330b1-138">В области данных будет отображена итоговая сумма продаж компании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Адаму Пауэлу.</span><span class="sxs-lookup"><span data-stu-id="330b1-138">The total sales of products by [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] to Adam Powell are displayed in the data area.</span></span>  
  
7.  <span data-ttu-id="330b1-139">Щелкните правой кнопкой мыши объем продаж, наведите указатель на пункт **Дополнительные действия**, а затем щелкните **Детализация сведений о заказе**.</span><span class="sxs-lookup"><span data-stu-id="330b1-139">Right-click on the sales amount, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="330b1-140">В окне **Средство просмотра выборки данных**приводятся подробные сведения о заказах, отправленных Адаму Пауэлу, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="330b1-140">The details of the orders that were shipped to Adam Powell are displayed in the **Data Sample Viewer**, as shown in the following image.</span></span> <span data-ttu-id="330b1-141">Однако были бы полезны некоторые дополнительные сведения, например дата заказа, дата оплаты счета и дата отгрузки.</span><span class="sxs-lookup"><span data-stu-id="330b1-141">However, some additional details would also be useful, such as the order date, due date, and ship date.</span></span> <span data-ttu-id="330b1-142">В следующей процедуре эти дополнительные сведения будут добавлены.</span><span class="sxs-lookup"><span data-stu-id="330b1-142">In the next procedure, you will add these additional details.</span></span>  
  
     <span data-ttu-id="330b1-143">![Заказы, доставленные Адаму Пауэлу](../../2014/tutorials/media/l8-action6.gif "Заказы, доставленные Адаму Пауэлу")</span><span class="sxs-lookup"><span data-stu-id="330b1-143">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action6.gif "Orders shipped to Adam Powell")</span></span>  
  
8.  <span data-ttu-id="330b1-144">Закрыть Excel/</span><span class="sxs-lookup"><span data-stu-id="330b1-144">Close Excel/</span></span>  
  
## <a name="modifying-the-drillthrough-action"></a><span data-ttu-id="330b1-145">Изменение действия детализации</span><span class="sxs-lookup"><span data-stu-id="330b1-145">Modifying the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="330b1-146">Откройте измерение **Подробности заказа через Интернет** в конструкторе измерений.</span><span class="sxs-lookup"><span data-stu-id="330b1-146">Open Dimension Designer for the **Internet Sales Order Details** dimension.</span></span>  
  
     <span data-ttu-id="330b1-147">Обратите внимание, что для этого измерения определены только три атрибута.</span><span class="sxs-lookup"><span data-stu-id="330b1-147">Notice that only three attributes have been defined for this dimension.</span></span>  
  
2.  <span data-ttu-id="330b1-148">На панели **Представление источника данных** щелкните правой кнопкой мыши свободную область и выберите команду **Показать все таблицы**.</span><span class="sxs-lookup"><span data-stu-id="330b1-148">In the **Data Source View** pane, right-click an open area, and then click **Show All Tables**.</span></span>  
  
3.  <span data-ttu-id="330b1-149">В меню **Формат** наведите указатель на пункт **Автомакет** и выберите пункт **Диаграмма**.</span><span class="sxs-lookup"><span data-stu-id="330b1-149">On the **Format** menu, point to **Autolayout** and then click **Diagram**.</span></span>  
  
4.  <span data-ttu-id="330b1-150">Найдите таблицу **InternetSales (dbo.FactInternetSales)** , щелкнув правой кнопкой мыши свободный участок панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="330b1-150">Locate the **InternetSales (dbo.FactInternetSales)** table by right-clicking in an open area of the **Data Source View** pane.</span></span> <span data-ttu-id="330b1-151">Выберите команду **Найти таблицу** , выберите **InternetSales** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="330b1-151">Then click **Find Table,** click **InternetSales,** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="330b1-152">Создайте новые атрибуты, основанные на следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="330b1-152">Create new attributes based on the following columns:</span></span>  
  
    -   <span data-ttu-id="330b1-153">OrderDateKey</span><span class="sxs-lookup"><span data-stu-id="330b1-153">OrderDateKey</span></span>  
  
    -   <span data-ttu-id="330b1-154">DueDateKey</span><span class="sxs-lookup"><span data-stu-id="330b1-154">DueDateKey</span></span>  
  
    -   <span data-ttu-id="330b1-155">ShipDateKey</span><span class="sxs-lookup"><span data-stu-id="330b1-155">ShipDateKey</span></span>  
  
6.  <span data-ttu-id="330b1-156">Измените значение свойства **имя** для **ключевого атрибута «Дата заказа** » на `Order Date` , нажмите кнопку обзора для свойства **Столбец имени** и в диалоговом окне **Столбец имени** выберите **Дата** в качестве исходной таблицы и выберите SimpleDate в качестве исходного столбца.</span><span class="sxs-lookup"><span data-stu-id="330b1-156">Change the **Name** property for the **Order Date Key** attribute to `Order Date` Then, click the browse button for the **Name Column** property, and in the **Name Column** dialog box, select **Date** as the source table and select SimpleDate as the source column.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="330b1-157">Измените свойство **Name** для **ключевого атрибута Дата выполнения** на `Due Date` , а затем с помощью того же метода, что и **ключевой атрибут даты заказа** , измените свойство **Column Name** для этого атрибута на **Date. SimpleDate (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="330b1-157">Change the **Name** property for the **Due Date Key** attribute to `Due Date`, and then, by using the same method as the **Order Date Key** attribute, change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
8.  <span data-ttu-id="330b1-158">Измените свойство **Name** для **ключевого атрибута Дата отгрузки** на `Ship Date` , а затем измените свойство **Column Name** для этого атрибута на **Date. SimpleDate (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="330b1-158">Change the **Name** property for the **Ship Date Key** attribute to `Ship Date`, and then change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
9. <span data-ttu-id="330b1-159">Перейдите на вкладку **Действия** конструктора кубов для куба "Учебник по [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ".</span><span class="sxs-lookup"><span data-stu-id="330b1-159">Switch to the **Actions** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
10. <span data-ttu-id="330b1-160">В поле **Столбцы детализации** установите флажки, добавив в список **Возвращаемые столбцы** перечисленные ниже столбцы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="330b1-160">In the **Drillthrough Columns** box, select the check boxes to add the following columns to the **Return Columns** list, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="330b1-161">Дата заказа</span><span class="sxs-lookup"><span data-stu-id="330b1-161">Order Date</span></span>  
  
    -   <span data-ttu-id="330b1-162">Срок заказа</span><span class="sxs-lookup"><span data-stu-id="330b1-162">Due Date</span></span>  
  
    -   <span data-ttu-id="330b1-163">Дата отгрузки</span><span class="sxs-lookup"><span data-stu-id="330b1-163">Ship Date</span></span>  
  
     <span data-ttu-id="330b1-164">На следующем рисунке эти столбцы выделены.</span><span class="sxs-lookup"><span data-stu-id="330b1-164">The following image shows these columns selected.</span></span>  
  
     <span data-ttu-id="330b1-165">![Поле «Столбцы детализации»](../../2014/tutorials/media/l8-action7.gif "Поле «Столбцы детализации»")</span><span class="sxs-lookup"><span data-stu-id="330b1-165">![Drillthrough Columns box](../../2014/tutorials/media/l8-action7.gif "Drillthrough Columns box")</span></span>  
  
## <a name="reviewing-the-modified-drillthrough-action"></a><span data-ttu-id="330b1-166">Просмотр измененного действия детализации</span><span class="sxs-lookup"><span data-stu-id="330b1-166">Reviewing the Modified Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="330b1-167">В меню **Сборка** выберите команду **Развернуть Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="330b1-167">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="330b1-168">После успешного завершения развертывания в конструкторе кубов, где открыт куб "Учебник по **", перейдите на вкладку** Браузер [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и нажмите кнопку **Повторное соединение** .</span><span class="sxs-lookup"><span data-stu-id="330b1-168">When deployment has successfully completed, switch to the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="330b1-169">Запустите Excel.</span><span class="sxs-lookup"><span data-stu-id="330b1-169">Start Excel.</span></span>  
  
4.  <span data-ttu-id="330b1-170">Создайте сводную таблицу снова с помощью меры **Продажи через Интернет — объем продаж** в области значений и **География заказчика** в фильтре отчета.</span><span class="sxs-lookup"><span data-stu-id="330b1-170">Recreate the PivotTable using **Internet Sales-Sales Amount** in the Values area and **Customer Geography** in the Report Filter.</span></span>  
  
     <span data-ttu-id="330b1-171">Добавьте фильтр по элементам **Все заказчики**, **Австралия**, **Квинсленд**, **Брисбен**, **4000**, **Адам Пауэл**.</span><span class="sxs-lookup"><span data-stu-id="330b1-171">Add a filter that selects from **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span></span>  
  
5.  <span data-ttu-id="330b1-172">Щелкните ячейку данных **Продажи через Интернет — объем продаж** , наведите указатель на пункт **Дополнительные действия**и щелкните **Детализация сведения о заказе**.</span><span class="sxs-lookup"><span data-stu-id="330b1-172">Click the **Internet Sales-Sales Amount** data cell, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="330b1-173">Подробные сведения о заказах, поставленных Адаму Пауэллу, отображаются на временном листе.</span><span class="sxs-lookup"><span data-stu-id="330b1-173">The details of these orders shipped to Adam Powell are displayed in a temporary worksheet.</span></span> <span data-ttu-id="330b1-174">Доступны для просмотра описание элемента, номер заказа, дата заказа, срок заказа и дата отгрузки, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="330b1-174">This includes item description, order number, order date, due date, and ship date information, as shown in the following image.</span></span>  
  
     <span data-ttu-id="330b1-175">![Заказы, доставленные Адаму Пауэлу](../../2014/tutorials/media/l8-action8.gif "Заказы, доставленные Адаму Пауэлу")</span><span class="sxs-lookup"><span data-stu-id="330b1-175">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action8.gif "Orders shipped to Adam Powell")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="330b1-176">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="330b1-176">Next Lesson</span></span>  
 [<span data-ttu-id="330b1-177">Урок 9. Определение перспектив и преобразований</span><span class="sxs-lookup"><span data-stu-id="330b1-177">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="330b1-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="330b1-178">See Also</span></span>  
 <span data-ttu-id="330b1-179">[Действия &#40;Analysis Services многомерных данных&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="330b1-179">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="330b1-180">[Действия в многомерных моделях](multidimensional-models/actions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="330b1-180">[Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="330b1-181">[Связи измерений](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="330b1-181">[Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 <span data-ttu-id="330b1-182">[Определение связи фактов](lesson-5-2-defining-a-fact-relationship.md) </span><span class="sxs-lookup"><span data-stu-id="330b1-182">[Defining a Fact Relationship](lesson-5-2-defining-a-fact-relationship.md) </span></span>  
 [<span data-ttu-id="330b1-183">Определение связей фактов и свойств связей фактов</span><span class="sxs-lookup"><span data-stu-id="330b1-183">Define a Fact Relationship and Fact Relationship Properties</span></span>](multidimensional-models/define-a-fact-relationship-and-fact-relationship-properties.md)  
  
  
