---
title: Учебник. Добавление в отчет ключевого показателя эффективности (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1bf77859-0b33-4f40-abaf-ebeeb6ebb1f8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 405978721068583597adf5c4257978a222121078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735937"
---
# <a name="tutorial-adding-a-kpi-to-your-report-report-builder"></a><span data-ttu-id="8204f-102">Учебник. Добавление в отчет ключевого показателя эффективности (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="8204f-102">Tutorial: Adding a KPI to Your Report (Report Builder)</span></span>
  <span data-ttu-id="8204f-103">Ключевой показатель эффективности (KPI) — это измеримое значение, имеющее деловую значимость.</span><span class="sxs-lookup"><span data-stu-id="8204f-103">A key performance indicator (KPI) is a measurable value that has business significance.</span></span> <span data-ttu-id="8204f-104">Этот учебник поможет научиться включать ключевые показатели эффективности в отчет.</span><span class="sxs-lookup"><span data-stu-id="8204f-104">This tutorial teaches you how to include a (KPI) in a report.</span></span> <span data-ttu-id="8204f-105">В данном случае ключевым показателем эффективности является сводка по продажам (по подкатегориям продуктов).</span><span class="sxs-lookup"><span data-stu-id="8204f-105">In this scenario, the sales summary by product subcategories is the KPI.</span></span> <span data-ttu-id="8204f-106">Текущее состояние ключевого показателя эффективности отображается с помощью цветов, датчиков и индикаторов.</span><span class="sxs-lookup"><span data-stu-id="8204f-106">The current state of the KPI is shown by using colors, gauges, and indicators.</span></span>  
  
 <span data-ttu-id="8204f-107">На приведенном далее рисунке показан отчет, который вам предстоит создать.</span><span class="sxs-lookup"><span data-stu-id="8204f-107">The following illustration shows the report that you will create.</span></span>  
  
 <span data-ttu-id="8204f-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span><span class="sxs-lookup"><span data-stu-id="8204f-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="8204f-109">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="8204f-109">What You Will Learn</span></span>  
 <span data-ttu-id="8204f-110">Этот учебник поможет научиться добавлять ключевой показатель эффективности путем задания цвета фона ячеек таблицы, исходя из значения каждой ячейки, и последующего добавления датчика и индикатора.</span><span class="sxs-lookup"><span data-stu-id="8204f-110">In this tutorial, you will learn to add a KPI by setting the background color of table cells based on cell value and add and configure a gauge and an indicator.</span></span> <span data-ttu-id="8204f-111">Кроме того, вы научитесь писать выражения, задающее цвет фона ячеек таблицы.</span><span class="sxs-lookup"><span data-stu-id="8204f-111">You also learn to write the expression that sets the background color of the table cells.</span></span>  
  
 <span data-ttu-id="8204f-112">Этот учебник описывает следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="8204f-112">This tutorial contains the following procedures:</span></span>  
  
1.  [<span data-ttu-id="8204f-113">Создание табличного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="8204f-113">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Table)  
  
2.  [<span data-ttu-id="8204f-114">Организация данных, выбор макета и стиля в мастере таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="8204f-114">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="8204f-115">Отображение ключевого показателя эффективности с помощью цветов фона</span><span class="sxs-lookup"><span data-stu-id="8204f-115">Use Background Colors to Display a KPI</span></span>](#BackgroundColors)  
  
4.  [<span data-ttu-id="8204f-116">Отображение ключевого показателя эффективности с помощью датчика</span><span class="sxs-lookup"><span data-stu-id="8204f-116">Display a KPI by Using a Gauge</span></span>](#Gauge)  
  
5.  [<span data-ttu-id="8204f-117">Отображение ключевого показателя эффективности с помощью индикатора</span><span class="sxs-lookup"><span data-stu-id="8204f-117">Display a KPI by Using an Indicator</span></span>](#Indicator)  
  
6.  [<span data-ttu-id="8204f-118">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="8204f-118">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="8204f-119">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="8204f-119">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="8204f-120">В данном учебнике стадии работы мастера объединены в две процедуры: для создания набора данных и для создания таблиц.</span><span class="sxs-lookup"><span data-stu-id="8204f-120">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="8204f-121">Пошаговые инструкции по переходу к серверу отчетов, выбору источника данных, созданию набора данных и запуску мастера см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8204f-121">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="8204f-122">Предполагаемое время для выполнения заданий этого учебника: 15 минут.</span><span class="sxs-lookup"><span data-stu-id="8204f-122">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8204f-123">Требования</span><span class="sxs-lookup"><span data-stu-id="8204f-123">Requirements</span></span>  
 <span data-ttu-id="8204f-124">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="8204f-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Table"></a><span data-ttu-id="8204f-125">1. Создание табличного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="8204f-125">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="8204f-126">В диалоговом окне **Начало работы** выберите общий источник данных, создайте внедренный набор данных и отобразите данные в таблице.</span><span class="sxs-lookup"><span data-stu-id="8204f-126">From the **Getting Started** dialog box, choose a shared data source, create an embedded dataset, and display the data in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8204f-127">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="8204f-127">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="8204f-128">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="8204f-128">This makes the query quite long.</span></span> <span data-ttu-id="8204f-129">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="8204f-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="8204f-130">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="8204f-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-table"></a><span data-ttu-id="8204f-131">Создание новой таблицы</span><span class="sxs-lookup"><span data-stu-id="8204f-131">To create a new table</span></span>  
  
1.  <span data-ttu-id="8204f-132">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="8204f-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="8204f-133">Откроется диалоговое окно **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="8204f-133">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8204f-134">Если диалоговое окно **Начало работы** не отображается, на кнопке Построитель отчетов нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="8204f-134">If the **Getting Started** dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="8204f-135">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="8204f-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="8204f-136">На панели справа выберите **Мастер таблицы или матрицы**.</span><span class="sxs-lookup"><span data-stu-id="8204f-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="8204f-137">На странице Выбор набора данных выберите **Создать набор данных**.</span><span class="sxs-lookup"><span data-stu-id="8204f-137">On the Choose a dataset page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="8204f-138">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8204f-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="8204f-139">На странице **Выбор соединения с источником данных** выберите существующий источник данных или перейдите к серверу отчетов и выберите источник данных.</span><span class="sxs-lookup"><span data-stu-id="8204f-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source.</span></span> <span data-ttu-id="8204f-140">Если отсутствуют доступные источники данных или доступ к серверу отчетов, можно воспользоваться внедренным источником данных.</span><span class="sxs-lookup"><span data-stu-id="8204f-140">If there no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="8204f-141">Дополнительные сведения см. в разделе [Учебник. Создание простого табличного отчета (построитель отчетов)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8204f-141">For more information, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="8204f-142">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8204f-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="8204f-143">На странице **Проектирование запроса** нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="8204f-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="8204f-144">Скопируйте и вставьте на панели запросов следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="8204f-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
10. <span data-ttu-id="8204f-145">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8204f-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="8204f-146">2. Упорядочивание данных, выбор макета и стиля в мастере таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="8204f-146">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="8204f-147">С помощью мастера начните конструировать отчет, в котором будут отображаться данные.</span><span class="sxs-lookup"><span data-stu-id="8204f-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="8204f-148">Панель предварительного просмотра в мастере позволяет визуализировать результат группирования данных до завершения конструирования таблицы или матрицы.</span><span class="sxs-lookup"><span data-stu-id="8204f-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-choose-a-layout-and-a-style"></a><span data-ttu-id="8204f-149">Разбиение данных по группам выберите макет и стиль</span><span class="sxs-lookup"><span data-stu-id="8204f-149">To organize data into groups, choose a layout and a style</span></span>  
  
1.  <span data-ttu-id="8204f-150">На странице "Размещение полей" перетащите поле "Продукт" в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="8204f-150">On the Arrange fields page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="8204f-151">Перетащите поле "Количество" в область **Значения** и поместите ниже поля "Продукт".</span><span class="sxs-lookup"><span data-stu-id="8204f-151">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="8204f-152">Сводные значения для поля Quantity вычисляются с помощью функции Sum, которая является функцией по умолчанию для вычисления сводных значений числовых полей.</span><span class="sxs-lookup"><span data-stu-id="8204f-152">Quantity is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
3.  <span data-ttu-id="8204f-153">Перетащите поле "Продажи" в область **Значения** и поместите ниже поля "Количество".</span><span class="sxs-lookup"><span data-stu-id="8204f-153">Drag Sales to **Values** and place below Quantity.</span></span>  
  
     <span data-ttu-id="8204f-154">Шаги 1, 2 и 3 задают данные, отображаемые в таблице.</span><span class="sxs-lookup"><span data-stu-id="8204f-154">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="8204f-155">Перетащите поле SalesDate в область **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="8204f-155">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="8204f-156">Перетащите поле "Подкатегория" в область **Группы строк** и поместите его ниже поля SalesDate.</span><span class="sxs-lookup"><span data-stu-id="8204f-156">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="8204f-157">Шаги 4 и 5 организуют значения полей сначала по дате, а потом по всем продажам для данной даты.</span><span class="sxs-lookup"><span data-stu-id="8204f-157">Steps 4 and 5 organize the values for the fields first by date, and then by all sales for that date.</span></span>  
  
6.  <span data-ttu-id="8204f-158">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8204f-158">Click **Next**.</span></span>  
  
     <span data-ttu-id="8204f-159">При выполнении отчета в таблице отображается каждая дата, все заказы для каждой даты и все продукты, количества и итоги по продажам для каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="8204f-159">When you run the report, the table displays each date, all orders for each date, and all products, quantities, and sales totals for each order.</span></span>  
  
7.  <span data-ttu-id="8204f-160">Убедитесь в том, что на странице "Выбор макета" в области **Параметры**выбран параметр **Показывать подытоги и общие итоги** .</span><span class="sxs-lookup"><span data-stu-id="8204f-160">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
8.  <span data-ttu-id="8204f-161">Убедитесь в том, что выбран параметр **Заблокированный, подытог ниже** .</span><span class="sxs-lookup"><span data-stu-id="8204f-161">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
9. <span data-ttu-id="8204f-162">Снимите флажок **Развернуть или свернуть группы**.</span><span class="sxs-lookup"><span data-stu-id="8204f-162">Clear the option **Expand/collapse groups**.</span></span>  
  
     <span data-ttu-id="8204f-163">В описываемом здесь отчете не используется функция углубленной детализации, которая позволяет пользователю разворачивать родительскую групповую иерархию, чтобы отобразить строки дочерней группы и строки подробностей.</span><span class="sxs-lookup"><span data-stu-id="8204f-163">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
10. <span data-ttu-id="8204f-164">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8204f-164">Click **Next**.</span></span>  
  
11. <span data-ttu-id="8204f-165">На странице «Выбор стиля» на панели «Стили» выберите стиль.</span><span class="sxs-lookup"><span data-stu-id="8204f-165">On the Choose a Style page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="8204f-166">На иллюстрации с законченным отчетом показан отчет в стиле «Аквамарин».</span><span class="sxs-lookup"><span data-stu-id="8204f-166">The illustration of the completed report shows the report using the Ocean style.</span></span>  
  
12. <span data-ttu-id="8204f-167">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8204f-167">Click **Finish**.</span></span>  
  
     <span data-ttu-id="8204f-168">Таблица добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="8204f-168">The table is added to the design surface.</span></span> <span data-ttu-id="8204f-169">Таблица содержит пять столбцов и пять строк.</span><span class="sxs-lookup"><span data-stu-id="8204f-169">The table has five columns and five rows.</span></span> <span data-ttu-id="8204f-170">Панель "Группы строк" содержит три группы строк: SalesDate, Subcategory и Details.</span><span class="sxs-lookup"><span data-stu-id="8204f-170">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="8204f-171">Подробные данные — это все данные, которые извлекаются с помощью запроса к набору данных.</span><span class="sxs-lookup"><span data-stu-id="8204f-171">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
13. <span data-ttu-id="8204f-172">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-172">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="8204f-173">Для каждого продукта, проданного за указанную дату, в таблице отображается название этого продукта, проданное количество и сумма продаж.</span><span class="sxs-lookup"><span data-stu-id="8204f-173">For each product that is sold on a specific date, the table displays the product name, the quantity sold, and the sales total.</span></span> <span data-ttu-id="8204f-174">Данные упорядочиваются сначала по дате продажи, а потом по подкатегории.</span><span class="sxs-lookup"><span data-stu-id="8204f-174">The data is organized first by sales date and then by subcategory.</span></span>  
  
##  <a name="3-use-background-colors-to-display-a-kpi"></a><a name="BackgroundColors"></a><span data-ttu-id="8204f-175">3. Отображение ключевого показателя эффективности с помощью цветов фона</span><span class="sxs-lookup"><span data-stu-id="8204f-175">3. Use Background Colors to Display a KPI</span></span>  
 <span data-ttu-id="8204f-176">Цвета фона можно задавать в виде выражений, вычисляемых при запуске отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-176">Background colors can be set to an expression that is evaluated when you run the report.</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-by-using-background-colors"></a><span data-ttu-id="8204f-177">Отображение текущего состояния ключевого показателя эффективности с помощью цвета фона</span><span class="sxs-lookup"><span data-stu-id="8204f-177">To display the present state of a KPI by using background colors</span></span>  
  
1.  <span data-ttu-id="8204f-178">В таблице щелкните правой кнопкой мыши две ячейки вниз от `[Sum(Sales)]` ячейки (строка промежуточного итога, отображающая продажи для подкатегории), а затем выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="8204f-178">In the table, right-click two cells down from the `[Sum(Sales)]` cell (the subtotal row that displays the sales for a subcategory), and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="8204f-179">В области **Заливка**нажмите кнопку **FX** рядом с параметром **Цвет заливки** и введите следующее выражение в поле **выражение набора для: BackgroundColor** :</span><span class="sxs-lookup"><span data-stu-id="8204f-179">In **Fill**, click the **fx** button next to the **Fill color** option and enter the following expression in the **Set expression for: BackgroundColor** field:</span></span>  
  
 `=IIF(Sum(Fields!Sales.Value) >= 5000 ,"Lime", IIF(Sum(Fields!Sales.Value) < 2500, "Red","Yellow"))`  
  
 <span data-ttu-id="8204f-180">Это изменяет цвет фона на зеленый с использованием оттенка зеленого «Lime» для каждой ячейки, содержащей итоговые суммы для `[Sum(Sales)]`, которые больше или равны 5 000.</span><span class="sxs-lookup"><span data-stu-id="8204f-180">This changes the background color to green, using the shade of green named "Lime", for each cell that contains an aggregated sum for `[Sum(Sales)]` that is greater than or equal to 5000.</span></span> <span data-ttu-id="8204f-181">Значения `[Sum(Sales)]` в диапазоне от 2 500 до 5 000 окрашены желтым цветом.</span><span class="sxs-lookup"><span data-stu-id="8204f-181">Values of `[Sum(Sales)]` between 2500 and 5000 are colored yellow.</span></span> <span data-ttu-id="8204f-182">Значения менее 2 500 окрашены красным цветом.</span><span class="sxs-lookup"><span data-stu-id="8204f-182">Values less than 2500 are colored red.</span></span>  
  
1.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="8204f-183">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-183">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="8204f-184">В строке промежуточных итогов, где отображаются продажи для подкатегории, цвет ячейки может быть красным, желтым или зеленым в зависимости от значения суммы продаж.</span><span class="sxs-lookup"><span data-stu-id="8204f-184">In the subtotal row that displays the sales for a subcategory, the background color of the cell is red, yellow, or green depending on value of the sales sum.</span></span>  
  
##  <a name="4-display-a-kpi-by-using-a-gauge"></a><a name="Gauge"></a><span data-ttu-id="8204f-185">4. Отображение ключевого показателя эффективности с помощью датчика</span><span class="sxs-lookup"><span data-stu-id="8204f-185">4. Display a KPI by Using a Gauge</span></span>  
 <span data-ttu-id="8204f-186">Датчик показывает одно значение из набора данных.</span><span class="sxs-lookup"><span data-stu-id="8204f-186">A gauge depicts a single value in a dataset.</span></span> <span data-ttu-id="8204f-187">В этом учебнике используется горизонтальный линейный датчик, поскольку его форма и простота облегчают его чтение, даже когда он имеет небольшой размер и помещен в ячейку таблицы.</span><span class="sxs-lookup"><span data-stu-id="8204f-187">This tutorial uses a horizontal linear gauge because its shape and simplicity makes it easy to read, even in when it is a small size and used within a table cell.</span></span> <span data-ttu-id="8204f-188">Дополнительные сведения см. в разделе [Датчики (построитель отчетов и службы SSRS)](report-design/gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8204f-188">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-a-gauge"></a><span data-ttu-id="8204f-189">Отображение текущего состояния ключевого показателя эффективности с помощью датчика</span><span class="sxs-lookup"><span data-stu-id="8204f-189">To display the present state of a KPI using a gauge</span></span>  
  
1.  <span data-ttu-id="8204f-190">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="8204f-190">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8204f-191">В таблице щелкните правой кнопкой мыши обработчик столбцов для ячейки, которая была изменена в предыдущей процедуре, наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **справа**.</span><span class="sxs-lookup"><span data-stu-id="8204f-191">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="8204f-192">В таблицу добавится новый столбец.</span><span class="sxs-lookup"><span data-stu-id="8204f-192">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="8204f-193">В заголовке столбца введите **ключевое поле KPI** .</span><span class="sxs-lookup"><span data-stu-id="8204f-193">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="8204f-194">На вкладке **Вставка** в группе **области данных** щелкните **датчик**, а затем щелкните область конструктора за пределами таблицы.</span><span class="sxs-lookup"><span data-stu-id="8204f-194">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click the design surface outside the table.</span></span> <span data-ttu-id="8204f-195">Откроется диалоговое окно **Выбор типа датчика** .</span><span class="sxs-lookup"><span data-stu-id="8204f-195">The **Select Gauge Type** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="8204f-196">Щелкните **Линейная**.</span><span class="sxs-lookup"><span data-stu-id="8204f-196">Click **Linear**.</span></span> <span data-ttu-id="8204f-197">Выбирается первый тип линейного датчика ( **Горизонтальный**).</span><span class="sxs-lookup"><span data-stu-id="8204f-197">The first linear gauge type, **Horizontal**, is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="8204f-198">В область конструктора добавится датчик.</span><span class="sxs-lookup"><span data-stu-id="8204f-198">A gauge is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="8204f-199">Перетащите поле Sales из области данных отчета на датчик.</span><span class="sxs-lookup"><span data-stu-id="8204f-199">From the Report Data pane, drag Sales to the gauge.</span></span> <span data-ttu-id="8204f-200">При перетаскивании поля Sales по датчику откроется панель «Данные датчика».</span><span class="sxs-lookup"><span data-stu-id="8204f-200">When you drag Sales across the gauge, the Gauge Data pane opens.</span></span>  
  
8.  <span data-ttu-id="8204f-201">Перетащите Sales в список **значения** .</span><span class="sxs-lookup"><span data-stu-id="8204f-201">Drop Sales in the **Values** list.</span></span>  
  
     <span data-ttu-id="8204f-202">Когда поле перетаскивается на датчик, его значение вычисляется с помощью встроенной функции Sum.</span><span class="sxs-lookup"><span data-stu-id="8204f-202">When you drop the field onto the gauge, the field is aggregated by using the built-in Sum function.</span></span>  
  
9. <span data-ttu-id="8204f-203">Щелкните правой кнопкой мыши указатель в датчике и выберите пункт **Свойства указателя**.</span><span class="sxs-lookup"><span data-stu-id="8204f-203">Right-click the pointer in the gauge and click **Pointer Properties**.</span></span>  
  
10. <span data-ttu-id="8204f-204">В списке **тип указателя**выберите **полоса**.</span><span class="sxs-lookup"><span data-stu-id="8204f-204">In **Pointer Type**, select **Bar**.</span></span> <span data-ttu-id="8204f-205">Указатель будет изменен с маркера на черту, это сделает его более видимым, когда в таблицу добавится датчик.</span><span class="sxs-lookup"><span data-stu-id="8204f-205">This changes the pointer from a marker to a bar that will be more visible when the gauge is added to the table.</span></span>  
  
11. <span data-ttu-id="8204f-206">Нажмите кнопку **Заливка указателя**.</span><span class="sxs-lookup"><span data-stu-id="8204f-206">Click **Pointer Fill**.</span></span> <span data-ttu-id="8204f-207">В **дополнительном цвете** выберите **желтый**.</span><span class="sxs-lookup"><span data-stu-id="8204f-207">In **Secondary Color,** pick **Yellow**.</span></span> <span data-ttu-id="8204f-208">Шаблон градиента заливки изменится с белого на желтый.</span><span class="sxs-lookup"><span data-stu-id="8204f-208">The gradient fill pattern will change from white to yellow.</span></span>  
  
12. <span data-ttu-id="8204f-209">Щелкните правой кнопкой мыши шкалу датчика и выберите пункт **Свойства шкалы**.</span><span class="sxs-lookup"><span data-stu-id="8204f-209">Right-click the scale in the gauge and click **Scale Properties**.</span></span>  
  
13. <span data-ttu-id="8204f-210">Установите для параметра **Максимальное** значение 25000.</span><span class="sxs-lookup"><span data-stu-id="8204f-210">Set the **Maximum** option to 25000.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8204f-211">Вместо константы (например, 25 000) можно использовать выражение для динамического вычисления значения параметра **Максимум** .</span><span class="sxs-lookup"><span data-stu-id="8204f-211">Instead of a constant such as 25000, you can use an expression to dynamically calculate the value of the **Maximum** option.</span></span> <span data-ttu-id="8204f-212">Оно является агрегатным выражением агрегатной функции и выглядит аналогично выражению `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span><span class="sxs-lookup"><span data-stu-id="8204f-212">The expression would use the aggregate of aggregate feature and look similar to the expression `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span></span>  
  
14. <span data-ttu-id="8204f-213">Перетащите датчик внутри таблицы в третью ячейку добавленного столбца, в строку промежуточных итогов, где отображаются продажи для подкатегории.</span><span class="sxs-lookup"><span data-stu-id="8204f-213">Drag the gauge inside the table into the third cell in the subtotal row that displays the sales for a subcategory of the column that you inserted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8204f-214">Возможно, придется изменить размер столбца, чтобы горизонтальный линейный датчик соответствовал по размеру ячейке.</span><span class="sxs-lookup"><span data-stu-id="8204f-214">You might have to resize the column so that the horizontal linear gauge fits into the cell.</span></span> <span data-ttu-id="8204f-215">Чтобы изменить размер столбца, щелкните заголовок столбца и используйте маркеры, чтобы изменить размеры ячейки по вертикали и горизонтали.</span><span class="sxs-lookup"><span data-stu-id="8204f-215">To resize the column, click a column header and use the handles to resize the cells horizontally and vertically.</span></span>  
  
15. <span data-ttu-id="8204f-216">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-216">Click **Run** to preview the report.</span></span>  
  
     <span data-ttu-id="8204f-217">Горизонтальная длина черты датчика изменяется в зависимости от значения ключевого показателя эффективности.</span><span class="sxs-lookup"><span data-stu-id="8204f-217">The horizontal length of the bar in the gauge changes depending on the value of the KPI.</span></span>  
  
16. <span data-ttu-id="8204f-218">(Дополнительно) Добавьте штифт-ограничитель для управления переполнением, чтобы любое значение, превосходящее максимальное значение шкалы, всегда указывало на штифт-ограничитель.</span><span class="sxs-lookup"><span data-stu-id="8204f-218">(Optional) Add a maximum pin to handle overflow so that any value over the scale maximum always points to the maximum pin:</span></span>  
  
    1.  <span data-ttu-id="8204f-219">Откройте панель «Свойства».</span><span class="sxs-lookup"><span data-stu-id="8204f-219">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="8204f-220">Щелкните шкалу.</span><span class="sxs-lookup"><span data-stu-id="8204f-220">Click the scale.</span></span> <span data-ttu-id="8204f-221">На панели «Свойства» отобразятся свойства линейной шкалы.</span><span class="sxs-lookup"><span data-stu-id="8204f-221">The properties for the linear scale are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="8204f-222">В категории " **ПИН-коды шкалы** " разверните узел **максимумпин** .</span><span class="sxs-lookup"><span data-stu-id="8204f-222">In the **Scale Pins** category, expand the **MaximumPin** node.</span></span>  
  
    4.  <span data-ttu-id="8204f-223">Задайте для свойства **включить** значение `True` .</span><span class="sxs-lookup"><span data-stu-id="8204f-223">Set the **Enable** property to `True`.</span></span> <span data-ttu-id="8204f-224">Ограничитель появляется за максимальным значением на шкале.</span><span class="sxs-lookup"><span data-stu-id="8204f-224">A pin appears after the maximum value on the scale.</span></span>  
  
    5.  <span data-ttu-id="8204f-225">Задайте для свойства **BorderColor** значение `Lime` .</span><span class="sxs-lookup"><span data-stu-id="8204f-225">Set **BorderColor** to `Lime`.</span></span>  
  
17. <span data-ttu-id="8204f-226">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-display-a-kpi-by-using-an-indicator"></a><a name="Indicator"></a><span data-ttu-id="8204f-227">5. Отображение ключевого показателя эффективности с помощью индикатора</span><span class="sxs-lookup"><span data-stu-id="8204f-227">5. Display a KPI by Using an Indicator</span></span>  
 <span data-ttu-id="8204f-228">Индикаторы — это небольшие простые датчики, позволяющие с первого взгляда получить представление о значениях данных.</span><span class="sxs-lookup"><span data-stu-id="8204f-228">Indicators are small simple gauges that communicate data values at a glance.</span></span> <span data-ttu-id="8204f-229">Из-за своего размера и простоты индикаторы часто используются в таблицах и матрицах.</span><span class="sxs-lookup"><span data-stu-id="8204f-229">Because of their size and simplicity, indicators are often used in tables and matrices.</span></span> <span data-ttu-id="8204f-230">Дополнительные сведения см. в разделе [Индикаторы (построитель отчетов и службы SSRS)](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8204f-230">For more information, see [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-an-indicator"></a><span data-ttu-id="8204f-231">Отображение текущего состояния ключевого показателя эффективности с помощью индикатора</span><span class="sxs-lookup"><span data-stu-id="8204f-231">To display the present state of a KPI using an indicator</span></span>  
  
1.  <span data-ttu-id="8204f-232">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="8204f-232">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8204f-233">В таблице щелкните правой кнопкой мыши обработчик столбцов для ячейки, которая была изменена в предыдущей процедуре, наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **справа**.</span><span class="sxs-lookup"><span data-stu-id="8204f-233">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="8204f-234">В таблицу добавится новый столбец.</span><span class="sxs-lookup"><span data-stu-id="8204f-234">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="8204f-235">В заголовке столбца введите **ключевое поле KPI** .</span><span class="sxs-lookup"><span data-stu-id="8204f-235">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="8204f-236">Щелкните ячейку подытога подкатегории.</span><span class="sxs-lookup"><span data-stu-id="8204f-236">Click the cell for the subcategory subtotal.</span></span>  
  
5.  <span data-ttu-id="8204f-237">На вкладке **Вставка** в группе **области данных** дважды щелкните элемент **индикатор.**</span><span class="sxs-lookup"><span data-stu-id="8204f-237">On the **Insert** tab, in the **Data Regions** group, double-click **Indicator.**</span></span>  
  
     <span data-ttu-id="8204f-238">Откроется диалоговое окно **Выбор стиля индикатора** .</span><span class="sxs-lookup"><span data-stu-id="8204f-238">The **Select Indicator Type** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="8204f-239">Щелкните **фигуры**.</span><span class="sxs-lookup"><span data-stu-id="8204f-239">Click **Shapes**.</span></span> <span data-ttu-id="8204f-240">Выбирается первый тип фигуры, **3 светофора (без обрамления)** .</span><span class="sxs-lookup"><span data-stu-id="8204f-240">The first shape type, **3 Traffic Lights (Unrimmed),** is selected.</span></span>  
  
     <span data-ttu-id="8204f-241">Именно этот индикатор и будет использоваться в данном учебнике.</span><span class="sxs-lookup"><span data-stu-id="8204f-241">You will use this indicator in the tutorial.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="8204f-242">Индикатор будет добавлен в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="8204f-242">The indicator is added to the design surface.</span></span>  
  
8.  <span data-ttu-id="8204f-243">Щелкните индикатор правой кнопкой мыши и выберите пункт **Свойства индикатора**.</span><span class="sxs-lookup"><span data-stu-id="8204f-243">Right-click the indicator and click **Indicator Properties**.</span></span>  
  
9. <span data-ttu-id="8204f-244">Щелкните **значения и состояния**.</span><span class="sxs-lookup"><span data-stu-id="8204f-244">Click **Values and States**.</span></span>  
  
10. <span data-ttu-id="8204f-245">В раскрывающемся списке значение выберите **[Sum (Sales)]**, но не изменяйте другие параметры.</span><span class="sxs-lookup"><span data-stu-id="8204f-245">In the Value drop-down list, select **[Sum(Sales)]**, but do not change any other options.</span></span>  
  
     <span data-ttu-id="8204f-246">По умолчанию синхронизация данных происходит в пределах области данных, а значение **Tablix1**, имя табличной области данных из отчета, отображается в поле **Область синхронизации** .</span><span class="sxs-lookup"><span data-stu-id="8204f-246">By default, data synchronization occurs across the data region and you see the value **Tablix1**, the name of the table data region in the report, in the **Synchronization scope** box.</span></span>  
  
     <span data-ttu-id="8204f-247">В этом отчете можно также изменить область индикатора, помещенного в ячейку подытога подкатегории, чтобы синхронизация выполнялась в поле SalesDate.</span><span class="sxs-lookup"><span data-stu-id="8204f-247">In this report, you can also change the scope of an indicator placed in the cell of the subcategory subtotal to synchronize across the SalesDate field.</span></span>  
  
11. <span data-ttu-id="8204f-248">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-248">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="8204f-249">6. Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="8204f-249">6. Add a Report Title</span></span>  
 <span data-ttu-id="8204f-250">Заголовок отчета отображается в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-250">A report title appears at the top of the report.</span></span> <span data-ttu-id="8204f-251">Можно поместить заголовок отчета в верхнем колонтитуле или, если в отчете колонтитулы не используются, в текстовом поле в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-251">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="8204f-252">Используется текстовое поле, которое автоматически размещается в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-252">You will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="8204f-253">Текст можно улучшить, применяя к отдельным символам различные стили шрифтов, размеры и цвета.</span><span class="sxs-lookup"><span data-stu-id="8204f-253">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="8204f-254">Дополнительные сведения см. в разделе [Форматирование текста в текстовом поле &#40;построитель отчетов и службы SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8204f-254">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="8204f-255">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="8204f-255">To add a report title</span></span>  
  
1.  <span data-ttu-id="8204f-256">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="8204f-256">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="8204f-257">Введите **ключевой показатель эффективности продаж продукта**и щелкните за пределами текстового поля.</span><span class="sxs-lookup"><span data-stu-id="8204f-257">Type **Product Sales KPI**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="8204f-258">При необходимости щелкните правой кнопкой мыши текстовое поле, содержащее **ключевой показатель эффективности продаж продукта**, выберите пункт **Свойства текстового поля**, а затем на вкладке Шрифт выберите различные начертания, размеры и цвета шрифта.</span><span class="sxs-lookup"><span data-stu-id="8204f-258">Optionally, right-click the text box that contains **Product Sales KPI**, click **Text Box Properties**, and then on the Font tab select the different font styles, sizes and colors.</span></span>  
  
4.  <span data-ttu-id="8204f-259">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="8204f-259">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="8204f-260">7. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="8204f-260">7. Save the Report</span></span>  
 <span data-ttu-id="8204f-261">Сохраните отчет на сервере отчетов или на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="8204f-261">Save the report to a report server or your computer.</span></span> <span data-ttu-id="8204f-262">Если не сохранить отчет на сервере отчетов, некоторые функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , в том числе элементы отчета и вложенные отчеты, будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="8204f-262">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="8204f-263">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="8204f-263">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="8204f-264">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="8204f-264">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="8204f-265">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="8204f-265">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="8204f-266">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="8204f-266">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="8204f-267">Появится сообщение «Соединение с сервером отчетов».</span><span class="sxs-lookup"><span data-stu-id="8204f-267">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="8204f-268">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов как место по умолчанию для отчетов.</span><span class="sxs-lookup"><span data-stu-id="8204f-268">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="8204f-269">В поле **Имя**замените имя по умолчанию фразой **Ключевой показатель эффективности продаж товаров**.</span><span class="sxs-lookup"><span data-stu-id="8204f-269">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
5.  <span data-ttu-id="8204f-270">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8204f-270">Click **Save**.</span></span>  
  
 <span data-ttu-id="8204f-271">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="8204f-271">The report is saved to the report server.</span></span> <span data-ttu-id="8204f-272">Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="8204f-272">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="8204f-273">Сохранение отчета на компьютере</span><span class="sxs-lookup"><span data-stu-id="8204f-273">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="8204f-274">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="8204f-274">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="8204f-275">Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="8204f-275">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8204f-276">При отсутствии доступа к серверу отчетов на **рабочем столе**откройте папку **Мои документы**или **Мой компьютер** и сохраните отчет на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8204f-276">If you do not have access to a report server, click **Desktop**, **My Documents**, or **My computer** and save the report to your computer.</span></span>  
  
1.  <span data-ttu-id="8204f-277">В поле **Имя**замените имя по умолчанию фразой **Ключевой показатель эффективности продаж товаров**.</span><span class="sxs-lookup"><span data-stu-id="8204f-277">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
2.  <span data-ttu-id="8204f-278">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8204f-278">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8204f-279">Next Steps</span><span class="sxs-lookup"><span data-stu-id="8204f-279">Next Steps</span></span>  
 <span data-ttu-id="8204f-280">Учебник «Добавление ключевого показателя эффективности в отчет» успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="8204f-280">You have successfully completed the Adding a KPI to Your Report tutorial.</span></span> <span data-ttu-id="8204f-281">Дополнительные сведения см. в разделе датчики датчиков (построитель отчетов) [&#40;построитель отчетов и службы SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8204f-281">For more information, see Gauges (Report Builder) [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8204f-282">См. также:</span><span class="sxs-lookup"><span data-stu-id="8204f-282">See Also</span></span>  
 <span data-ttu-id="8204f-283">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="8204f-283">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="8204f-284">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8204f-284">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
