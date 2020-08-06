---
title: Учебник. Добавление параметра к отчету (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eab34ec4-b3ad-4a76-95cc-07b2f75ee6d7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dff41066a2d505ab53b17a10fb3da9b6cb17130f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735953"
---
# <a name="tutorial-add-a-parameter-to-your-report-report-builder"></a><span data-ttu-id="41e60-102">Учебник. Добавление параметра к отчету (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="41e60-102">Tutorial: Add a Parameter to Your Report (Report Builder)</span></span>
  <span data-ttu-id="41e60-103">Добавление в отчет параметра позволяет пользователям фильтровать в нем данные, полученные из источника данных.</span><span class="sxs-lookup"><span data-stu-id="41e60-103">Add a parameter to your report to let users filter report data from the data source or in the report.</span></span> <span data-ttu-id="41e60-104">Параметры отчета создаются автоматически для каждого параметра запроса, включенного в запрос к набору данных.</span><span class="sxs-lookup"><span data-stu-id="41e60-104">Report parameters are created automatically for each query parameter that you include in a dataset query.</span></span> <span data-ttu-id="41e60-105">От типа данных параметра зависит то, как он будет выглядеть на панели инструментов средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="41e60-105">The parameter data type determines how it appears on the report view toolbar.</span></span>  
  
 <span data-ttu-id="41e60-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span><span class="sxs-lookup"><span data-stu-id="41e60-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="41e60-107">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="41e60-107">What You Will Learn</span></span>  
 <span data-ttu-id="41e60-108">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="41e60-108">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="41e60-109">Создание матричного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="41e60-109">Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="41e60-110">Организация данных, выбор макета и стиля в мастере таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="41e60-110">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="41e60-111">Добавьте параметр запроса, чтобы создать параметр отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-111">Add a Query Parameter to Create a Report Parameter</span></span>](#Query)  
  
4.  [<span data-ttu-id="41e60-112">Изменение типа данных по умолчанию и других свойств параметра отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-112">Change Default Data Type and Other Properties for a Report Parameter</span></span>](#ChangeDefaultProperties)  
  
    1.  [<span data-ttu-id="41e60-113">Добавление набора данных для отображения значений и отображаемых имен</span><span class="sxs-lookup"><span data-stu-id="41e60-113">Add a Dataset to Provide Available Values and Display Names</span></span>](#AddDataset)  
  
    2.  [<span data-ttu-id="41e60-114">Задание доступных значений для создания раскрывающегося списка значений</span><span class="sxs-lookup"><span data-stu-id="41e60-114">Specify Available Values to Create a Drop-List of Values</span></span>](#AvailableValues)  
  
    3.  [<span data-ttu-id="41e60-115">Задание значений по умолчанию для автоматического выполнения отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-115">Specify Default Values so the Report Runs Automatically</span></span>](#DefaultValues)  
  
    4.  [<span data-ttu-id="41e60-116">Поиск значения в наборе данных, содержащем пары имя-значение</span><span class="sxs-lookup"><span data-stu-id="41e60-116">Look up a Value from a Dataset that has Name/Value Pairs</span></span>](#NameValue)  
  
5.  [<span data-ttu-id="41e60-117">Отображение значения выбранного параметра в отчете</span><span class="sxs-lookup"><span data-stu-id="41e60-117">Display the Selected Parameter Value in the Report</span></span>](#Expression)  
  
6.  [<span data-ttu-id="41e60-118">Использование параметра отчета в фильтре</span><span class="sxs-lookup"><span data-stu-id="41e60-118">Use the Report Parameter in a Filter</span></span>](#Filter)  
  
7.  [<span data-ttu-id="41e60-119">Изменение параметра отчета для принятия нескольких значений</span><span class="sxs-lookup"><span data-stu-id="41e60-119">Change the Report Parameter to Accept Multiple Values</span></span>](#Multivalued)  
  
8.  [<span data-ttu-id="41e60-120">Добавление логического параметра для обеспечения условной видимости</span><span class="sxs-lookup"><span data-stu-id="41e60-120">Add a Boolean Parameter for Conditional Visibility</span></span>](#Boolean)  
  
9. [<span data-ttu-id="41e60-121">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-121">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="41e60-122">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-122">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="41e60-123">В этом учебнике шаги работы с мастером объединены в одну процедуру.</span><span class="sxs-lookup"><span data-stu-id="41e60-123">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="41e60-124">Пошаговые инструкции по переходу к серверу отчетов, выбору источника данных и созданию набора данных см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="41e60-124">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="41e60-125">Предполагаемое время для выполнения заданий данного учебника: 25 минут.</span><span class="sxs-lookup"><span data-stu-id="41e60-125">Estimated time to complete this tutorial: 25 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41e60-126">Требования</span><span class="sxs-lookup"><span data-stu-id="41e60-126">Requirements</span></span>  
 <span data-ttu-id="41e60-127">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="41e60-127">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="41e60-128">1. Создание матричного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="41e60-128">1. Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="41e60-129">Создайте матричный отчет, источник данных и набор данных.</span><span class="sxs-lookup"><span data-stu-id="41e60-129">Create a matrix report, a data source, and a dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41e60-130">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="41e60-130">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="41e60-131">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="41e60-131">This makes the query quite long.</span></span> <span data-ttu-id="41e60-132">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="41e60-132">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="41e60-133">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="41e60-133">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix-report"></a><span data-ttu-id="41e60-134">Создание нового матричного отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-134">To create a new matrix report</span></span>  
  
1.  <span data-ttu-id="41e60-135">Нажмите кнопку **Пуск**, укажите пункт **программы**, выберите пункт [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Построитель отчетов**, а затем щелкните **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="41e60-135">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="41e60-136">Откроется диалоговое окно **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="41e60-136">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="41e60-137">Если диалоговое окно **Начало работы** не отображается, на кнопке **Построитель отчетов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="41e60-137">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="41e60-138">Убедитесь, что на панели слева выбран пункт **Отчет** .</span><span class="sxs-lookup"><span data-stu-id="41e60-138">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="41e60-139">На панели справа выберите **Мастер таблицы или матрицы**.</span><span class="sxs-lookup"><span data-stu-id="41e60-139">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="41e60-140">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="41e60-140">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="41e60-141">На странице **Выбор набора данных** выберите **Создать набор данных**.</span><span class="sxs-lookup"><span data-stu-id="41e60-141">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
6.  <span data-ttu-id="41e60-142">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41e60-142">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="41e60-143">На странице **Выбор соединения с источником данных** выберите источник данных, имеющий тип **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="41e60-143">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="41e60-144">Выберите источник данных из списка или перейдите на сервер отчетов, чтобы выбрать его там.</span><span class="sxs-lookup"><span data-stu-id="41e60-144">Select a data source from the list or browse to the report server to select one.</span></span>  
  
8.  <span data-ttu-id="41e60-145">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41e60-145">Click **Next**.</span></span>  
  
9. <span data-ttu-id="41e60-146">На странице **Проектирование запроса** нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="41e60-146">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
10. <span data-ttu-id="41e60-147">На панель запроса вставьте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="41e60-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    ;WITH CTE (StoreID, Subcategory, Quantity)   
    AS (  
    SELECT 200 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 2002 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Camcorders' AS Subcategory, 1954 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Accessories' AS Subcategory, 1895 AS Quantity  
    UNION SELECT  199 AS StoreID, 'Digital Cameras' AS Subcategory, 1849 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1579 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Camcorders' AS Subcategory, 1561 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital Cameras' AS Subcategory, 1553 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Accessories' AS Subcategory, 1534 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Accessories' AS Subcategory, 1755 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Camcorders' AS Subcategory, 1631 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1772 AS Quantity)  
    SELECT StoreID, Subcategory, Quantity  
    FROM CTE  
    ```  
  
     <span data-ttu-id="41e60-148">Этот запрос сочетает результаты нескольких инструкций SELECT языка [!INCLUDE[tsql](../includes/tsql-md.md)] внутри обобщенного табличного выражения, определяя значения, в основе которых лежат упрощенные данные из образца базы данных Contoso.</span><span class="sxs-lookup"><span data-stu-id="41e60-148">This query combines the results of several [!INCLUDE[tsql](../includes/tsql-md.md)] SELECT statements inside a common table expression to specify values that are based on simplified data from the Contoso sample database.</span></span> <span data-ttu-id="41e60-149">Данные о продажах компании Contoso представляют данные о международных продажах товаров широкого потребления.</span><span class="sxs-lookup"><span data-stu-id="41e60-149">The Contoso sales data represents international sales data for consumer goods.</span></span> <span data-ttu-id="41e60-150">В этом учебнике используются данные о продажах фотоаппаратов.</span><span class="sxs-lookup"><span data-stu-id="41e60-150">This tutorial uses sales data for cameras.</span></span> <span data-ttu-id="41e60-151">Подкатегории представляют цифровые фотоаппараты, цифровые однообъективные зеркальные фотоаппараты, видеокамеры и аксессуары.</span><span class="sxs-lookup"><span data-stu-id="41e60-151">The subcategories represent digital cameras, digital single lens reflex (SLR) cameras, camcorders, and accessories.</span></span>  
  
     <span data-ttu-id="41e60-152">Запрос определяет имена столбцов, включающие идентификатор магазина, подкатегорию товара и число продаж, сортируя данные по заказам на продажу от трех магазинов.</span><span class="sxs-lookup"><span data-stu-id="41e60-152">The query specifies column names that include a store identifier, a sales item subcategory, and the quantity ordered for sales orders from three stores.</span></span> <span data-ttu-id="41e60-153">В данном запросе имя магазина не входит в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="41e60-153">In this query, the store name is not part of the result set.</span></span> <span data-ttu-id="41e60-154">Позднее в этом учебнике будет выполнен поиск имени магазина, соответствующего идентификатору магазина, в отдельном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="41e60-154">Later in this tutorial, you will look up the name of the store that corresponds to the store identifier from a separate dataset.</span></span>  
  
     <span data-ttu-id="41e60-155">Этот запрос не содержит параметров.</span><span class="sxs-lookup"><span data-stu-id="41e60-155">This query does not contain query parameters.</span></span> <span data-ttu-id="41e60-156">Параметры запроса будут добавлены позже, в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="41e60-156">You will add query parameters later in this tutorial.</span></span>  
  
11. <span data-ttu-id="41e60-157">На панели инструментов конструктора запросов нажмите кнопку **выполнить** (**!**).</span><span class="sxs-lookup"><span data-stu-id="41e60-157">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="41e60-158">Результирующий набор отображает 11 строк данных, которые показывают количество товаров, проданных для каждой подкатегории четырех магазинов, и включает следующие столбцы: StoreID, Подкатегория, Quantity.</span><span class="sxs-lookup"><span data-stu-id="41e60-158">The result set displays 11 rows of data that show the quantity of items sold for each subcategory for four stores, and includes the following columns: StoreID, Subcategory, Quantity.</span></span>  
  
12. <span data-ttu-id="41e60-159">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41e60-159">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="41e60-160">2. Упорядочивание данных, выбор макета и стиля в мастере таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="41e60-160">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="41e60-161">С помощью мастера начните конструировать отчет, в котором будут отображаться данные.</span><span class="sxs-lookup"><span data-stu-id="41e60-161">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="41e60-162">Панель предварительного просмотра в мастере позволяет визуализировать результат группирования данных до завершения конструирования таблицы или матрицы.</span><span class="sxs-lookup"><span data-stu-id="41e60-162">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="41e60-163">Организация данных в группы</span><span class="sxs-lookup"><span data-stu-id="41e60-163">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="41e60-164">На странице **Размещение полей** перетащите поле "Субкатегория" в область **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="41e60-164">On the **Arrange fields** page, drag Subcategory to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="41e60-165">Перетащите поле "StoreID" в область **Группы столбцов**.</span><span class="sxs-lookup"><span data-stu-id="41e60-165">Drag StoreID to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="41e60-166">Перетащите поле "Количество" в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="41e60-166">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="41e60-167">Значения числа продаж организованы в строки, сгруппированные по подкатегориям.</span><span class="sxs-lookup"><span data-stu-id="41e60-167">You have organized the quantity sold values in rows grouped by subcategory.</span></span> <span data-ttu-id="41e60-168">Каждому магазину будет соответствовать один столбец.</span><span class="sxs-lookup"><span data-stu-id="41e60-168">There will be one column for each store.</span></span>  
  
4.  <span data-ttu-id="41e60-169">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41e60-169">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="41e60-170">На странице **Выбор макета** в области **Параметры**убедитесь в том, что выбран параметр **Показать подытоги и общие итоги** .</span><span class="sxs-lookup"><span data-stu-id="41e60-170">On the **Choose a Layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="41e60-171">При запуске отчета последний столбец будет содержать общее число продаж по каждой категории для всех магазинов, а последняя строка — общее число продаж по всем подкатегориям для каждого магазина.</span><span class="sxs-lookup"><span data-stu-id="41e60-171">When you run the report, the last column will show the total quantity of each subcategory for all stores, and the last row will show the total quantity for all subcategories for each store.</span></span>  
  
6.  <span data-ttu-id="41e60-172">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41e60-172">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="41e60-173">На панели Стили на странице **Выбор стиля** выберите стиль.</span><span class="sxs-lookup"><span data-stu-id="41e60-173">On the **Choose a Style** page, in the Styles pane, select a style.</span></span>  
  
8.  <span data-ttu-id="41e60-174">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="41e60-174">Click **Finish**.</span></span>  
  
     <span data-ttu-id="41e60-175">Матрица добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-175">The matrix is added to the design surface.</span></span> <span data-ttu-id="41e60-176">Она содержит три столбца и три строки.</span><span class="sxs-lookup"><span data-stu-id="41e60-176">The matrix displays three columns and three rows.</span></span> <span data-ttu-id="41e60-177">В ячейках первой строки содержатся поля Subcategory, [StoreID] и Total.</span><span class="sxs-lookup"><span data-stu-id="41e60-177">The contents of the cells in the first row are Subcategory, [StoreID], and Total.</span></span> <span data-ttu-id="41e60-178">В ячейках второй строки содержатся выражения, представляющие подкатегорию, число продаж для каждого магазина, а также итог по каждой из подкатегорий для всех магазинов.</span><span class="sxs-lookup"><span data-stu-id="41e60-178">The contents of the cells in the second row contain expressions that represent the subcategory, the quantity of items sold for each store, and the total quantity for each subcategory for all stores.</span></span> <span data-ttu-id="41e60-179">В ячейках последней строки отображаются общие итоги для каждого магазина.</span><span class="sxs-lookup"><span data-stu-id="41e60-179">The cells in the final row display the grand total for each store.</span></span>  
  
9. <span data-ttu-id="41e60-180">Щелкните в пределах матрицы, наведите курсор на край первого столбца, захватите маркер и увеличьте ширину столбца.</span><span class="sxs-lookup"><span data-stu-id="41e60-180">Click in the matrix, hover over the edge of the first column, grab the handle, and expand the column width.</span></span>  
  
10. <span data-ttu-id="41e60-181">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="41e60-181">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="41e60-182">Отчет будет запущен на сервере отчетов; также будет отображен заголовок и время обработки отчета.</span><span class="sxs-lookup"><span data-stu-id="41e60-182">The report runs on the report server and displays the title and the time the report processing occurred.</span></span>  
  
 <span data-ttu-id="41e60-183">В этом сценарии в заголовках столбцов отображается идентификатор магазина, а не его имя.</span><span class="sxs-lookup"><span data-stu-id="41e60-183">In this scenario, the column headings display the store identifier but not the store name.</span></span> <span data-ttu-id="41e60-184">Позднее будет добавлено выражение для поиска имени магазина в наборе данных, содержащем пары идентификатор магазина — имя магазина.</span><span class="sxs-lookup"><span data-stu-id="41e60-184">Later, you will add an expression to look up the store name in a dataset that contains store identifier/store name pairs.</span></span>  
  
##  <a name="3-add-a-query-parameter-to-create-a-report-parameter"></a><a name="Query"></a><span data-ttu-id="41e60-185">3. Добавление параметра запроса для создания параметра отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-185">3. Add a Query Parameter to Create a Report Parameter</span></span>  
 <span data-ttu-id="41e60-186">При добавлении в запрос параметра запроса построитель отчетов автоматически создает однозначный параметр отчета, устанавливая его свойства имени, приглашения и типа данных в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41e60-186">When you add a query parameter to a query, Report Builder automatically creates a single-valued report parameter with default properties for name, prompt, and data type.</span></span>  
  
#### <a name="to-add-a-query-parameter"></a><span data-ttu-id="41e60-187">Добавление параметра запроса</span><span class="sxs-lookup"><span data-stu-id="41e60-187">To add a query parameter</span></span>  
  
1.  <span data-ttu-id="41e60-188">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-188">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-189">В области данных отчета разверните папку **Наборы данных** , щелкните правой кнопкой мыши набор данных **DataSet1**и выберите пункт **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="41e60-189">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
3.  <span data-ttu-id="41e60-190">Добавьте следующее [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` предложение в качестве последней строки запроса:</span><span class="sxs-lookup"><span data-stu-id="41e60-190">Add the following [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause as the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID = (@StoreID)  
    ```  
  
     <span data-ttu-id="41e60-191">`WHERE`Предложение ограничивает извлеченные данные идентификатором магазина, указанным в параметре запроса *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="41e60-191">The `WHERE` clause limits the retrieved data to the store identifier that is specified by the query parameter *@StoreID*.</span></span>  
  
4.  <span data-ttu-id="41e60-192">На панели инструментов конструктора запросов нажмите кнопку **выполнить** (**!**).</span><span class="sxs-lookup"><span data-stu-id="41e60-192">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="41e60-193">Откроется диалоговое окно **Определение параметров запроса** и предложит ввести значение параметра запроса *@StoreID*.</span><span class="sxs-lookup"><span data-stu-id="41e60-193">The **Define Query Parameters** dialog box opens and prompts for a value for the query parameter *@StoreID*.</span></span>  
  
5.  <span data-ttu-id="41e60-194">В поле **Значение параметра**введите **200**.</span><span class="sxs-lookup"><span data-stu-id="41e60-194">In **Parameter Value**, type **200**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="41e60-195">Результирующий набор отображает число продаж для аксессуаров, видеокамер и цифровых однообъективных зеркальных фотоаппаратов в магазине с идентификатором **200**.</span><span class="sxs-lookup"><span data-stu-id="41e60-195">The result set displays the quantities sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="41e60-196">В области данных отчета разверните папку **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="41e60-196">In the Report Data pane, expand the **Parameters** folder.</span></span>  
  
 <span data-ttu-id="41e60-197">Обратите внимание, что теперь имеется параметр отчета с именем *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="41e60-197">Notice that there is now a report parameter named *@StoreID*.</span></span> <span data-ttu-id="41e60-198">По умолчанию он имеет тип данных **Text**.</span><span class="sxs-lookup"><span data-stu-id="41e60-198">By default, the parameter has data type **Text**.</span></span> <span data-ttu-id="41e60-199">Поскольку идентификатор магазина является целым числом, в следующей процедуре тип данных будет изменен на Integer.</span><span class="sxs-lookup"><span data-stu-id="41e60-199">Because the store identifier is an integer, you will change the data type to Integer in the next procedure.</span></span>  
  
##  <a name="4-change-default-data-type-and-other-properties-for-a-report-parameter"></a><a name="ChangeDefaultProperties"></a><span data-ttu-id="41e60-200">4. изменение типа данных по умолчанию и других свойств для параметра отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-200">4. Change Default Data Type and Other Properties for a Report Parameter</span></span>  
 <span data-ttu-id="41e60-201">После создания параметра отчета можно настроить значения его свойств, заданные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41e60-201">After a report parameter is created, you can adjust the default values for properties.</span></span>  
  
#### <a name="to-change-the-default-data-type-for-a-report-parameter"></a><span data-ttu-id="41e60-202">Смена типа данных по умолчанию для параметра отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-202">To change the default data type for a report parameter</span></span>  
  
1.  <span data-ttu-id="41e60-203">В области данных отчета в узле **Параметры** щелкните правой кнопкой мыши *@StoreID* и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="41e60-203">In the Report Data pane under the **Parameters** node, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="41e60-204">В поле Запрос введите **идентификатор магазина.**</span><span class="sxs-lookup"><span data-stu-id="41e60-204">In Prompt, type **Store identifier?**</span></span> <span data-ttu-id="41e60-205">Этот текст появится на панели инструментов средства просмотра отчетов при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="41e60-205">This text appears on the report viewer toolbar when you run the report.</span></span>  
  
3.  <span data-ttu-id="41e60-206">В раскрывающемся списке **Тип данных**выберите **Integer**.</span><span class="sxs-lookup"><span data-stu-id="41e60-206">In **Data type**, from the drop-down list, select **Integer**.</span></span>  
  
4.  <span data-ttu-id="41e60-207">Примите для оставшихся параметров в диалоговом окне значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="41e60-207">Accept the remaining default values in the dialog box.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="41e60-208">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-208">Preview the report.</span></span> <span data-ttu-id="41e60-209">В средстве просмотра отчетов отобразится запрос *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="41e60-209">The report viewer displays the prompt for *@StoreID*.</span></span>  
  
7.  <span data-ttu-id="41e60-210">На панели инструментов средства просмотра отчетов введите для параметра Store ID значение **200**и нажмите **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="41e60-210">On the report viewer toolbar, next to Store ID, type **200**, and then click **View Report**.</span></span>  
  
##  <a name="4a-add-a-dataset-to-provide-available-values-and-display-names"></a><a name="AddDataset"></a><span data-ttu-id="41e60-211">4A.</span><span class="sxs-lookup"><span data-stu-id="41e60-211">4a.</span></span> <span data-ttu-id="41e60-212">Добавление набора данных для отображения значений и отображаемых имен</span><span class="sxs-lookup"><span data-stu-id="41e60-212">Add a Dataset to Provide Available Values and Display Names</span></span>  
 <span data-ttu-id="41e60-213">Чтобы гарантировать, что пользователи смогут ввести только допустимые значения для параметра, можно создать раскрывающийся список, из которого будут выбираться значения.</span><span class="sxs-lookup"><span data-stu-id="41e60-213">To ensure a user can type only valid values for a parameter, you can create a drop-down list of values to choose from.</span></span> <span data-ttu-id="41e60-214">Значения могут поступать из набора данных или из указанного списка.</span><span class="sxs-lookup"><span data-stu-id="41e60-214">The values can come from a dataset or from a list that you specify.</span></span> <span data-ttu-id="41e60-215">Доступные значения должны предоставляться набором данных, имеющим запрос, не содержащий ссылку на параметр.</span><span class="sxs-lookup"><span data-stu-id="41e60-215">Available values must be supplied from a dataset that has a query that does not contain a reference to the parameter.</span></span>  
  
#### <a name="to-create-a-dataset-for-valid-values-for-a-parameter"></a><span data-ttu-id="41e60-216">Создание набора данных с допустимыми значениями для параметра</span><span class="sxs-lookup"><span data-stu-id="41e60-216">To create a dataset for valid values for a parameter</span></span>  
  
1.  <span data-ttu-id="41e60-217">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-217">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-218">В области данных отчета щелкните правой кнопкой мыши папку **Наборы данных** и выберите команду **Добавить набор данных**.</span><span class="sxs-lookup"><span data-stu-id="41e60-218">In the Report Data pane, right-click the **Datasets** folder, and then click **Add Dataset**.</span></span>  
  
3.  <span data-ttu-id="41e60-219">В поле **Имя**введите **Магазины**.</span><span class="sxs-lookup"><span data-stu-id="41e60-219">In **Name**, type **Stores**.</span></span>  
  
4.  <span data-ttu-id="41e60-220">Выберите параметр **Использовать набор данных, внедренный в отчет** .</span><span class="sxs-lookup"><span data-stu-id="41e60-220">Select the **Use a dataset embedded in my report** option.</span></span>  
  
5.  <span data-ttu-id="41e60-221">В раскрывающемся списке **Источник данных**, выберите источник данных, созданный в ходе выполнения первой процедуры.</span><span class="sxs-lookup"><span data-stu-id="41e60-221">In **Data source**, from the drop-down list, choose the data source you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="41e60-222">Убедитесь, что в списке **Тип запроса**выбран тип **Текст** .</span><span class="sxs-lookup"><span data-stu-id="41e60-222">In **Query type**, verify that **Text** is selected.</span></span>  
  
7.  <span data-ttu-id="41e60-223">В поле **Запрос**вставьте следующий текст:</span><span class="sxs-lookup"><span data-stu-id="41e60-223">In **Query**, paste the following text:</span></span>  
  
    ```  
    SELECT 200 AS StoreID, 'Contoso Catalog Store' as StoreName  
    UNION SELECT 199 AS StoreID, 'Contoso North America Online Store' as StoreName  
    UNION SELECT 307 AS StoreID, 'Contoso Asia Online Store' as StoreName  
    UNION SELECT 306 AS StoreID, 'Contoso Europe Online Store' as StoreName  
    ```  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="41e60-224">В области данных отчета в узле **Stores** набора данных отображаются поля StoreID и StoreName.</span><span class="sxs-lookup"><span data-stu-id="41e60-224">The Report Data pane displays the fields StoreID and StoreName under the **Stores** dataset node.</span></span>  
  
##  <a name="4b-specify-available-values-to-create-a-drop-down-list-of-values"></a><a name="AvailableValues"></a><span data-ttu-id="41e60-225">4b.</span><span class="sxs-lookup"><span data-stu-id="41e60-225">4b.</span></span> <span data-ttu-id="41e60-226">Задание доступных значений для создания раскрывающегося списка значений</span><span class="sxs-lookup"><span data-stu-id="41e60-226">Specify Available Values to Create a Drop-down List of Values</span></span>  
 <span data-ttu-id="41e60-227">После создания набора данных для выбора доступных значений необходимо изменить свойства отчета, указав набор данных и поле, которые будут использоваться для заполнения раскрывающегося списка допустимыми значениями на панели инструментов reportviewer.</span><span class="sxs-lookup"><span data-stu-id="41e60-227">After you create a dataset to provide available values, you must change the report properties to specify which dataset and which field to use to populate the drop-down list of valid values on the reportviewer toolbar.</span></span>  
  
#### <a name="to-provide-available-values-for-a-parameter-from-a-dataset"></a><span data-ttu-id="41e60-228">Получение доступных значений параметра из набора данных</span><span class="sxs-lookup"><span data-stu-id="41e60-228">To provide available values for a parameter from a dataset</span></span>  
  
1.  <span data-ttu-id="41e60-229">В области данных отчета щелкните правой кнопкой мыши параметр *@StoreID* и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="41e60-229">In the Report Data pane, right-click the parameter *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="41e60-230">Нажмите кнопку **Допустимые значения**, а затем **Получать значения из запроса**.</span><span class="sxs-lookup"><span data-stu-id="41e60-230">Click **Available Values**, and then click **Get values from a query**.</span></span>  
  
3.  <span data-ttu-id="41e60-231">Из раскрывающегося списка **Набор данных**выберите **Stores**.</span><span class="sxs-lookup"><span data-stu-id="41e60-231">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
4.  <span data-ttu-id="41e60-232">Из раскрывающегося списка **Поле значения**выберите StoreID.</span><span class="sxs-lookup"><span data-stu-id="41e60-232">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
5.  <span data-ttu-id="41e60-233">Из раскрывающегося списка **Поле метки**выберите StoreName.</span><span class="sxs-lookup"><span data-stu-id="41e60-233">In **Label field**, from the drop-down list, click StoreName.</span></span> <span data-ttu-id="41e60-234">Поле метки указывает отображаемое имя для значения.</span><span class="sxs-lookup"><span data-stu-id="41e60-234">The label field specifies the display name for the value.</span></span>  
  
6.  <span data-ttu-id="41e60-235">Щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="41e60-235">Click **General**.</span></span>  
  
7.  <span data-ttu-id="41e60-236">В поле «Запрос» введите **Название магазина**.</span><span class="sxs-lookup"><span data-stu-id="41e60-236">In Prompt, type **Store name?**</span></span>  
  
     <span data-ttu-id="41e60-237">Теперь пользователь будет выбирать из списка название магазина, а не идентификатор.</span><span class="sxs-lookup"><span data-stu-id="41e60-237">The user will now select from a list of store names instead of store identifiers.</span></span> <span data-ttu-id="41e60-238">Обратите внимание, что типом данных остается **Integer** , поскольку параметр основан на идентификаторе магазина, а не на его имени.</span><span class="sxs-lookup"><span data-stu-id="41e60-238">Note that the parameter data type remains **Integer** because the parameter is based on the store identifier, not the store name.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="41e60-239">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-239">Preview the report.</span></span>  
  
     <span data-ttu-id="41e60-240">В панели инструментов средства просмотра отчетов текстовое поле параметр теперь содержит раскрывающийся список **\<Select a Value>** .</span><span class="sxs-lookup"><span data-stu-id="41e60-240">In the report viewer toolbar, the parameter text box is now a drop-down list that displays **\<Select a Value>**.</span></span>  
  
10. <span data-ttu-id="41e60-241">Выберите в этом списке значение «Contoso Catalog Store» и нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="41e60-241">From the drop-down list, select Contoso Catalog Store, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="41e60-242">Отчет отображает число продаж для аксессуаров, видеокамер и цифровых однообъективных зеркальных фотоаппаратов в магазине с идентификатором **200**.</span><span class="sxs-lookup"><span data-stu-id="41e60-242">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4c-specify-default-values-so-the-report-runs-automatically"></a><a name="DefaultValues"></a><span data-ttu-id="41e60-243">4c.</span><span class="sxs-lookup"><span data-stu-id="41e60-243">4c.</span></span> <span data-ttu-id="41e60-244">Задание значений по умолчанию для автоматического выполнения отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-244">Specify Default Values so the Report Runs Automatically</span></span>  
 <span data-ttu-id="41e60-245">Можно указать значения по умолчанию для каждого параметра, чтобы обеспечить автоматическое выполнение отчета.</span><span class="sxs-lookup"><span data-stu-id="41e60-245">You can specify a default value for each parameter so the report runs automatically.</span></span>  
  
#### <a name="to-specify-a-default-value-from-a-dataset"></a><span data-ttu-id="41e60-246">Указание значения по умолчанию из набора данных</span><span class="sxs-lookup"><span data-stu-id="41e60-246">To specify a default value from a dataset</span></span>  
  
1.  <span data-ttu-id="41e60-247">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-247">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-248">В области данных отчета щелкните правой кнопкой мыши *@StoreID* и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="41e60-248">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="41e60-249">Нажмите кнопку **Значения по умолчанию**, а затем **Получать значения из запроса**.</span><span class="sxs-lookup"><span data-stu-id="41e60-249">Click **Default Values**, and then click **Get values from a query**.</span></span>  
  
4.  <span data-ttu-id="41e60-250">Из раскрывающегося списка **Набор данных**выберите **Stores**.</span><span class="sxs-lookup"><span data-stu-id="41e60-250">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
5.  <span data-ttu-id="41e60-251">Из раскрывающегося списка **Поле значения**выберите StoreID.</span><span class="sxs-lookup"><span data-stu-id="41e60-251">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="41e60-252">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-252">Preview the report.</span></span>  
  
 <span data-ttu-id="41e60-253">Для *@StoreID* средство просмотра отчетов отображает значение "Contoso Северная Америка Online Store".</span><span class="sxs-lookup"><span data-stu-id="41e60-253">For *@StoreID*, the report viewer displays the value "Contoso North America Online Store".</span></span> <span data-ttu-id="41e60-254">Это первое значение из результирующего набора для набора данных **Stores**.</span><span class="sxs-lookup"><span data-stu-id="41e60-254">This is the first value from the result set for the dataset **Stores**.</span></span> <span data-ttu-id="41e60-255">Отчет отображает число продаж цифровых фотоаппаратов в магазине с идентификатором **199**.</span><span class="sxs-lookup"><span data-stu-id="41e60-255">The report displays the quantity sold for Digital Cameras for store identifier **199**.</span></span>  
  
#### <a name="to-specify-a-custom-default-value"></a><span data-ttu-id="41e60-256">Задание пользовательского значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="41e60-256">To specify a custom default value</span></span>  
  
1.  <span data-ttu-id="41e60-257">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-257">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-258">В области данных отчета щелкните правой кнопкой мыши *@StoreID* и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="41e60-258">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="41e60-259">Нажмите кнопку **Значения по умолчанию**, **Указать значения**, а затем **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="41e60-259">Click **Default Values**, and click **Specify values**, and then click **Add**.</span></span> <span data-ttu-id="41e60-260">Добавляется строка нового значения.</span><span class="sxs-lookup"><span data-stu-id="41e60-260">A new value row is added.</span></span>  
  
4.  <span data-ttu-id="41e60-261">В поле **Значение**введите **200**.</span><span class="sxs-lookup"><span data-stu-id="41e60-261">In **Value**, type **200**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="41e60-262">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-262">Preview the report.</span></span>  
  
 <span data-ttu-id="41e60-263">Для *@StoreID* средство просмотра отчетов отображает значение "магазин каталога Contoso".</span><span class="sxs-lookup"><span data-stu-id="41e60-263">For *@StoreID*, the report viewer displays the value "Contoso Catalog Store".</span></span> <span data-ttu-id="41e60-264">Это отображаемое имя для магазина с идентификатором **200**.</span><span class="sxs-lookup"><span data-stu-id="41e60-264">This is the display name for store identifier **200**.</span></span> <span data-ttu-id="41e60-265">Отчет отображает число продаж для аксессуаров, видеокамер и цифровых однообъективных зеркальных фотоаппаратов в магазине с идентификатором **200**.</span><span class="sxs-lookup"><span data-stu-id="41e60-265">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4d-look-up-a-value-from-a-dataset-that-has-namevalue-pairs"></a><a name="NameValue"></a><span data-ttu-id="41e60-266">4D.</span><span class="sxs-lookup"><span data-stu-id="41e60-266">4d.</span></span> <span data-ttu-id="41e60-267">Поиск значения в наборе данных, содержащем пары имя-значение</span><span class="sxs-lookup"><span data-stu-id="41e60-267">Look up a Value from a Dataset that has Name/Value Pairs</span></span>  
 <span data-ttu-id="41e60-268">Набор данных может содержать как идентификатор, так и соответствующее поле имени.</span><span class="sxs-lookup"><span data-stu-id="41e60-268">A dataset might contain both the identifier and the corresponding name field.</span></span> <span data-ttu-id="41e60-269">Если доступен только идентификатор, то можно найти соответствующее имя в созданном наборе данных, содержащем пары имя-значение.</span><span class="sxs-lookup"><span data-stu-id="41e60-269">When you only have an identifier, you can look up the corresponding name in a dataset that you created that includes name/value pairs.</span></span>  
  
#### <a name="to-look-up-a-value-from-a-dataset"></a><span data-ttu-id="41e60-270">Поиск значения в наборе данных</span><span class="sxs-lookup"><span data-stu-id="41e60-270">To look up a value from a dataset</span></span>  
  
1.  <span data-ttu-id="41e60-271">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-271">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-272">В области конструктора в заголовке столбца в первой строке матрицы щелкните правой кнопкой мыши `[StoreID]` и выберите пункт **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="41e60-272">On the design surface, in the matrix, in the first row column header, right-click `[StoreID]` and then click **Expression**.</span></span>  
  
3.  <span data-ttu-id="41e60-273">На панели выражения удалите весь текст, кроме начального `equals` (=).</span><span class="sxs-lookup"><span data-stu-id="41e60-273">In the expression pane, delete all text except the beginning `equals` (=).</span></span>  
  
4.  <span data-ttu-id="41e60-274">В узле **Категория**разверните **Общие функции**и щелкните **Разное**.</span><span class="sxs-lookup"><span data-stu-id="41e60-274">In **Category**, expand **Common Functions**, and click **Miscellaneous**.</span></span> <span data-ttu-id="41e60-275">На панели «Элемент» отображается набор функций.</span><span class="sxs-lookup"><span data-stu-id="41e60-275">The Item pane displays a set of functions.</span></span>  
  
5.  <span data-ttu-id="41e60-276">На панели "Элемент" дважды щелкните **Lookup**.</span><span class="sxs-lookup"><span data-stu-id="41e60-276">In Item, double-click **Lookup**.</span></span> <span data-ttu-id="41e60-277">На панели выражений появится `=Lookup(`.</span><span class="sxs-lookup"><span data-stu-id="41e60-277">The expression pane displays `=Lookup(`.</span></span> <span data-ttu-id="41e60-278">На панели примеров отображается пример синтаксиса функции Lookup.</span><span class="sxs-lookup"><span data-stu-id="41e60-278">The Example pane displays an example of Lookup syntax.</span></span>  
  
6.  <span data-ttu-id="41e60-279">Введите следующее выражение: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span><span class="sxs-lookup"><span data-stu-id="41e60-279">Type the following expression: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span></span>  
  
     <span data-ttu-id="41e60-280">Функция Lookup принимает значение StoreID, ищет его в наборе данных «Stores» и возвращает значение StoreName.</span><span class="sxs-lookup"><span data-stu-id="41e60-280">The Lookup function takes the value for StoreID, looks it up in the "Stores" dataset, and returns the StoreName value.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="41e60-281">Заголовок столбца Store содержит отображаемый текст для сложного выражения: **<\<Expr>>** .</span><span class="sxs-lookup"><span data-stu-id="41e60-281">The store column header contains the display text for a complex expression: **<\<Expr>>**.</span></span>  
  
8.  <span data-ttu-id="41e60-282">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-282">Preview the report.</span></span>  
  
 <span data-ttu-id="41e60-283">В текстовом поле вверху каждой страницы отображается имя магазина, а не его идентификатор.</span><span class="sxs-lookup"><span data-stu-id="41e60-283">The text box at the top of each page displays the store name instead of the store identifier.</span></span>  
  
##  <a name="5-display-the-selected-parameter-value-in-the-report"></a><a name="Expression"></a><span data-ttu-id="41e60-284">5. Отображение значения выбранного параметра в отчете</span><span class="sxs-lookup"><span data-stu-id="41e60-284">5. Display the Selected Parameter Value in the Report</span></span>  
 <span data-ttu-id="41e60-285">Если у пользователя появятся вопросы насчет отчета, полезно знать, какие значения параметров были им выбраны.</span><span class="sxs-lookup"><span data-stu-id="41e60-285">When a user has questions about a report, it helps to know which parameter values they chose.</span></span> <span data-ttu-id="41e60-286">Можно сохранить выбранные пользователем значения для каждого параметра отчета.</span><span class="sxs-lookup"><span data-stu-id="41e60-286">You can preserve user-selected values for each parameter in the report.</span></span> <span data-ttu-id="41e60-287">Один из способов — отображение параметров в текстовом поле в нижнем колонтитуле страницы.</span><span class="sxs-lookup"><span data-stu-id="41e60-287">One way is to display the parameters in a text box in the page footer.</span></span>  
  
#### <a name="to-display-the-selected-parameter-value-and-label-on-a-page-footer"></a><span data-ttu-id="41e60-288">Отображение значения выбранного параметра и его метки в нижнем колонтитуле страницы</span><span class="sxs-lookup"><span data-stu-id="41e60-288">To display the selected parameter value and label on a page footer</span></span>  
  
1.  <span data-ttu-id="41e60-289">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-289">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-290">Щелкните нижний колонтитул страницы правой кнопкой мыши, укажите **Вставить**и выберите пункт **Текстовое поле**.</span><span class="sxs-lookup"><span data-stu-id="41e60-290">Right-click the page footer, point to **Insert**, and then click **Text Box**.</span></span> <span data-ttu-id="41e60-291">Перетащите это текстовое поле к текстовому полю с отметкой времени.</span><span class="sxs-lookup"><span data-stu-id="41e60-291">Drag the text box next to the text box with the time stamp.</span></span> <span data-ttu-id="41e60-292">С помощью маркера текстового поля раздвиньте его в ширину.</span><span class="sxs-lookup"><span data-stu-id="41e60-292">Grab the side handle of the text box and expand the width.</span></span>  
  
3.  <span data-ttu-id="41e60-293">В области данных отчета перетащите параметр *@StoreID* в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="41e60-293">From the Report Data pane, drag the parameter *@StoreID* to the text box.</span></span> <span data-ttu-id="41e60-294">В текстовом поле отображается `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="41e60-294">The text box displays `[@StoreID]`.</span></span>  
  
4.  <span data-ttu-id="41e60-295">Чтобы отобразить метку параметра, щелкните текстовое поле несколько раз, пока курсор не появится после существующего выражения, а затем введите пробел и еще раз перетащите в текстовое поле копию параметра из области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="41e60-295">To display the parameter label, click in the text box until the insert cursor appears after the existing expression, type a space, and then drag another copy of the parameter from the Report Data pane to the text box.</span></span> <span data-ttu-id="41e60-296">В текстовом поле отображается `[@StoreID] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="41e60-296">The text box displays `[@StoreID] [@StoreID]`.</span></span>  
  
5.  <span data-ttu-id="41e60-297">Щелкните правой кнопкой мыши первое выражение и выберите команду **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="41e60-297">Right-click the first expression and click **Expression**.</span></span> <span data-ttu-id="41e60-298">Откроется диалоговое окно **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="41e60-298">The **Expression** dialog box opens.</span></span> <span data-ttu-id="41e60-299">Замените текст `Value` текстом `Label`.</span><span class="sxs-lookup"><span data-stu-id="41e60-299">Replace the text `Value` by `Label`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="41e60-300">Теперь текст содержит: `[@StoreID.Label] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="41e60-300">The text displays: `[@StoreID.Label] [@StoreID]`.</span></span>  
  
7.  <span data-ttu-id="41e60-301">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-301">Preview the report.</span></span>  
  
##  <a name="6-use-the-report-parameter-in-a-filter"></a><a name="Filter"></a><span data-ttu-id="41e60-302">6. Использование параметра отчета в фильтре</span><span class="sxs-lookup"><span data-stu-id="41e60-302">6. Use the Report Parameter in a Filter</span></span>  
 <span data-ttu-id="41e60-303">Фильтры помогают управлять тем, какие данные будут использованы в отчете после выборки из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="41e60-303">Filters help control which data to use in a report after it is retrieved from an external data source.</span></span> <span data-ttu-id="41e60-304">Чтобы позволить пользователям управлять отображаемыми данными, можно включить параметр отчета в фильтр для матрицы.</span><span class="sxs-lookup"><span data-stu-id="41e60-304">To let a user help control the data they want to see, you can include the report parameter in a filter for the matrix.</span></span>  
  
#### <a name="to-specify-a-parameter-in-a-matrix-filter"></a><span data-ttu-id="41e60-305">Задание параметра в фильтре матрицы</span><span class="sxs-lookup"><span data-stu-id="41e60-305">To specify a parameter in a matrix filter</span></span>  
  
1.  <span data-ttu-id="41e60-306">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-306">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-307">Щелкните правой кнопкой мыши маркер заголовка строки или столбца матрицы и выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="41e60-307">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="41e60-308">Выберите **Фильтры**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="41e60-308">Click **Filters**, and then click **Add**.</span></span> <span data-ttu-id="41e60-309">Появится строка нового фильтра.</span><span class="sxs-lookup"><span data-stu-id="41e60-309">A new filter row appears.</span></span>  
  
4.  <span data-ttu-id="41e60-310">В раскрывающемся списке **Выражение**выберите поле набора данных StoreID.</span><span class="sxs-lookup"><span data-stu-id="41e60-310">In **Expression**, from the drop-down list, select the dataset field StoreID.</span></span> <span data-ttu-id="41e60-311">Оно имеет тип данных **Integer**.</span><span class="sxs-lookup"><span data-stu-id="41e60-311">The data type displays **Integer**.</span></span> <span data-ttu-id="41e60-312">Если значением выражения является поле набора данных, то тип данных устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="41e60-312">When the expression value is a dataset field, the data type is set automatically.</span></span>  
  
5.  <span data-ttu-id="41e60-313">Убедитесь, что в списке **оператор** `equals` выбрано значение (=).</span><span class="sxs-lookup"><span data-stu-id="41e60-313">In **Operator**, verify that `equals` (=) is selected.</span></span>  
  
6.  <span data-ttu-id="41e60-314">В разделе **Значение** введите `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="41e60-314">In **Value**, type `[@StoreID]`.</span></span> <span data-ttu-id="41e60-315">`[@StoreID]` — это простой синтаксис выражения, представляющего `=Parameters!StoreID.Value`.</span><span class="sxs-lookup"><span data-stu-id="41e60-315">`[@StoreID]` is the simple expression syntax that represents `=Parameters!StoreID.Value`.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="41e60-316">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-316">Preview the report.</span></span>  
  
     <span data-ttu-id="41e60-317">В матрице будут отображены данные только о магазине «Contoso Catalog Store».</span><span class="sxs-lookup"><span data-stu-id="41e60-317">The matrix displays data only for "Contoso Catalog Store".</span></span>  
  
9. <span data-ttu-id="41e60-318">На панели инструментов средства просмотра отчетов в области **Название магазина:** выберите **Contoso Asia Online Store**, затем нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="41e60-318">On the report viewer toolbar, for **Store name?**, select **Contoso Asia Online Store**, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="41e60-319">В матрице будут отображены данные, соответствующие выбранному магазину.</span><span class="sxs-lookup"><span data-stu-id="41e60-319">The matrix displays data that corresponds to the store that you selected.</span></span>  
  
##  <a name="7-change-the-report-parameter-to-accept-multiple-values"></a><a name="Multivalued"></a><span data-ttu-id="41e60-320">7. изменение параметра отчета для принятия нескольких значений</span><span class="sxs-lookup"><span data-stu-id="41e60-320">7. Change the Report Parameter to Accept Multiple Values</span></span>  
 <span data-ttu-id="41e60-321">Чтобы изменить параметр с однозначного на многозначный, необходимо изменить запрос и все выражения, содержащие ссылку на параметр, включая фильтры.</span><span class="sxs-lookup"><span data-stu-id="41e60-321">To change a parameter from single to multivalued, you must change the query, and all expressions that contain a reference to the parameter, including filters.</span></span> <span data-ttu-id="41e60-322">Многозначный параметр — это массив значений.</span><span class="sxs-lookup"><span data-stu-id="41e60-322">A multivalued parameter is an array of values.</span></span> <span data-ttu-id="41e60-323">В запросе набора данных синтаксис запроса должен выполнять проверку на включение одного значения в набор значений.</span><span class="sxs-lookup"><span data-stu-id="41e60-323">In a dataset query, query syntax must test for inclusion of one value in a set of values.</span></span> <span data-ttu-id="41e60-324">В выражении отчета синтаксис выражения должен выполнять доступ к массиву значений, а не к отдельному значению.</span><span class="sxs-lookup"><span data-stu-id="41e60-324">In a report expression, expression syntax must access an array of values instead of an individual value.</span></span>  
  
#### <a name="to-change-a-parameter-from-single-to-multivalued"></a><span data-ttu-id="41e60-325">Изменение параметра с однозначного на многозначный</span><span class="sxs-lookup"><span data-stu-id="41e60-325">To change a parameter from single to multivalued</span></span>  
  
1.  <span data-ttu-id="41e60-326">Переключитесь в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="41e60-326">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="41e60-327">В области данных отчета щелкните правой кнопкой мыши *@StoreID* и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="41e60-327">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="41e60-328">Выберите **Разрешить несколько значений**.</span><span class="sxs-lookup"><span data-stu-id="41e60-328">Select **Allow multiple values**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="41e60-329">В области данных отчета разверните папку **Наборы данных** , щелкните правой кнопкой мыши набор данных **DataSet1**и выберите пункт **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="41e60-329">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
6.  <span data-ttu-id="41e60-330">Замените `equals` (=) на `IN` в [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` предложении в последней строке запроса:</span><span class="sxs-lookup"><span data-stu-id="41e60-330">Change `equals` (=) to `IN` in the [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause in the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID IN (@StoreID)  
    ```  
  
     <span data-ttu-id="41e60-331">Оператор `IN` выполняет проверку того, входит ли значение в набор значений.</span><span class="sxs-lookup"><span data-stu-id="41e60-331">The `IN` operator tests a value for inclusion in a set of values.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="41e60-332">Щелкните правой кнопкой мыши маркер заголовка строки или столбца матрицы и выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="41e60-332">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
9. <span data-ttu-id="41e60-333">Перейдите на вкладку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="41e60-333">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="41e60-334">В списке **Оператор**выберите **In**.</span><span class="sxs-lookup"><span data-stu-id="41e60-334">In **Operator**, select **In**.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="41e60-335">В текстовом поле, отображающем параметр (в нижнем колонтитуле страницы), удалите весь текст.</span><span class="sxs-lookup"><span data-stu-id="41e60-335">In the text box that displays the parameter in the page footer, delete all text.</span></span>  
  
13. <span data-ttu-id="41e60-336">Щелкните правой кнопкой мыши текстовое поле и выберите пункт **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="41e60-336">Right-click the text box, and then click **Expression**.</span></span> <span data-ttu-id="41e60-337">Введите следующее выражение: `=Join(Parameters!StoreID.Label, ", ")`</span><span class="sxs-lookup"><span data-stu-id="41e60-337">Type the following expression: `=Join(Parameters!StoreID.Label, ", ")`</span></span>  
  
     <span data-ttu-id="41e60-338">Это выражение объединяет все имена магазинов, выбранные пользователем.</span><span class="sxs-lookup"><span data-stu-id="41e60-338">This expression concatenates all store names that the user selected.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
15. <span data-ttu-id="41e60-339">Щелкните текстовое поле перед созданным выражением и введите следующее: «Выбранные значения параметров:».</span><span class="sxs-lookup"><span data-stu-id="41e60-339">Click in the text box in front of the expression that you just created, and then type the following: Parameter Values Selected:.</span></span>  
  
16. <span data-ttu-id="41e60-340">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-340">Preview the report.</span></span>  
  
17. <span data-ttu-id="41e60-341">Щелкните раскрывающийся список рядом с параметром «Имя магазина:».</span><span class="sxs-lookup"><span data-stu-id="41e60-341">Click the drop-down list next to Store Name?</span></span>  
  
     <span data-ttu-id="41e60-342">Каждое допустимое значение будет отображено рядом с флажком.</span><span class="sxs-lookup"><span data-stu-id="41e60-342">Each valid value appears next to a check box.</span></span>  
  
18. <span data-ttu-id="41e60-343">Установите флажок **Выбрать все**и нажмите кнопку **Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="41e60-343">Click **Select All**, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="41e60-344">В отчете будет отображено число продаж для всех подкатегорий всех магазинов.</span><span class="sxs-lookup"><span data-stu-id="41e60-344">The report displays the quantity sold for all subcategories for all stores.</span></span>  
  
19. <span data-ttu-id="41e60-345">В раскрывающемся списке снимите флажок **Выбрать все** , чтобы очистить список, установите флажки "Contoso Catalog Store" и "Contoso Asia Online Store", а затем нажмите кнопку **Просмотр отчета**.</span><span class="sxs-lookup"><span data-stu-id="41e60-345">From the drop-down list, click **Select All** to clear the list, click "Contoso Catalog Store" and "Contoso Asia Online Store", and then click **View Report**.</span></span>  
  
##  <a name="8-add-a-boolean-parameter-for-conditional-visibility"></a><a name="Boolean"></a><span data-ttu-id="41e60-346">8. Добавление логического параметра для условной видимости</span><span class="sxs-lookup"><span data-stu-id="41e60-346">8. Add a Boolean Parameter for Conditional Visibility</span></span>  
  
#### <a name="to-add-a-boolean-parameter"></a><span data-ttu-id="41e60-347">Добавление логического параметра</span><span class="sxs-lookup"><span data-stu-id="41e60-347">To add a boolean parameter</span></span>  
  
1.  <span data-ttu-id="41e60-348">В области конструктора в области данных отчета щелкните правой кнопкой мыши **Параметры**и выберите команду **Добавить параметр**.</span><span class="sxs-lookup"><span data-stu-id="41e60-348">On the design surface, in the Report Data pane, right-click **Parameters**, and click **Add Parameter**.</span></span>  
  
2.  <span data-ttu-id="41e60-349">В поле **Имя**введите «ShowSelections».</span><span class="sxs-lookup"><span data-stu-id="41e60-349">In **Name**, type ShowSelections.</span></span>  
  
3.  <span data-ttu-id="41e60-350">В поле **Запрос**введите «Показать выбранные?»</span><span class="sxs-lookup"><span data-stu-id="41e60-350">In **Prompt**, type Show selections?</span></span>  
  
4.  <span data-ttu-id="41e60-351">В раскрывающемся списке **Тип данных**выберите **Boolean**.</span><span class="sxs-lookup"><span data-stu-id="41e60-351">In **Data type**, from the drop-down list, click **Boolean**.</span></span>  
  
5.  <span data-ttu-id="41e60-352">Нажмите кнопку **Значения по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="41e60-352">Click **Default Values**.</span></span>  
  
6.  <span data-ttu-id="41e60-353">Щелкните **Задать значение**затем **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="41e60-353">Click **Specify value**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="41e60-354">В поле **Значение**введите **False**.</span><span class="sxs-lookup"><span data-stu-id="41e60-354">In **Value**, type **False**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-set-visibility-based-on-a-boolean-parameter"></a><span data-ttu-id="41e60-355">Задание видимости на основе логического параметра</span><span class="sxs-lookup"><span data-stu-id="41e60-355">To set visibility based on a boolean parameter</span></span>  
  
1.  <span data-ttu-id="41e60-356">В области конструктора в нижнем колонтитуле страницы щелкните правой кнопкой мыши текстовое поле, в котором отображаются значения параметров, и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="41e60-356">On the design surface, right-click the text box in the page footer that displays the parameter values, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="41e60-357">Щелкните **Видимость**.</span><span class="sxs-lookup"><span data-stu-id="41e60-357">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="41e60-358">Выберите параметр **Отображать или скрывать в зависимости от выражения**и нажмите кнопку выражения **Fx**.</span><span class="sxs-lookup"><span data-stu-id="41e60-358">Select the option **Show or hide based on an expression**, and then click the expression button **Fx**.</span></span>  
  
4.  <span data-ttu-id="41e60-359">Введите следующее выражение: `=Not Parameters!ShowSelections.Value`</span><span class="sxs-lookup"><span data-stu-id="41e60-359">Type the following expression: `=Not Parameters!ShowSelections.Value`</span></span>  
  
     <span data-ttu-id="41e60-360">Параметр «Видимость» текстового поля управляется свойством Hidden.</span><span class="sxs-lookup"><span data-stu-id="41e60-360">The text box Visibility option is controlled by the property Hidden.</span></span> <span data-ttu-id="41e60-361">Примените оператор `Not`, чтобы при выборе параметра свойство Hidden имело значение FALSE, а текстовое поле отображалось.</span><span class="sxs-lookup"><span data-stu-id="41e60-361">Apply the `Not` operator so that when the parameter is selected, the Hidden property is false, and the text box will be displayed.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="41e60-362">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-362">Preview the report.</span></span>  
  
     <span data-ttu-id="41e60-363">Текстовое поле, содержащее варианты параметров, не отображается.</span><span class="sxs-lookup"><span data-stu-id="41e60-363">The text box that displays the parameter choices does not appear.</span></span>  
  
8.  <span data-ttu-id="41e60-364">На панели инструментов средства просмотра отчетов, рядом с пунктом **отображать варианты выбора**нажмите кнопку `True` .</span><span class="sxs-lookup"><span data-stu-id="41e60-364">In the report viewer toolbar, next to **Show selections**, click `True`.</span></span>  
  
9. <span data-ttu-id="41e60-365">Просмотрите отчет.</span><span class="sxs-lookup"><span data-stu-id="41e60-365">Preview the report.</span></span>  
  
 <span data-ttu-id="41e60-366">В текстовом поле в нижнем колонтитуле страницы отображаются все выбранные имена магазинов.</span><span class="sxs-lookup"><span data-stu-id="41e60-366">The text box in the page footer displays all the store names that you selected.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="41e60-367">9. Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-367">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="41e60-368">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-368">To add a report title</span></span>  
  
1.  <span data-ttu-id="41e60-369">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="41e60-369">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="41e60-370">Введите «Параметризованные продажи продукта» и щелкните за пределами текстового поля.</span><span class="sxs-lookup"><span data-stu-id="41e60-370">Type Parameterized Product Sales, and then click outside the text box.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="41e60-371">10. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="41e60-371">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="41e60-372">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="41e60-372">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="41e60-373">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="41e60-373">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="41e60-374">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="41e60-374">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="41e60-375">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="41e60-375">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="41e60-376">Появится сообщение **Подключение к серверу отчетов**.</span><span class="sxs-lookup"><span data-stu-id="41e60-376">The message **Connecting to report server appears**.</span></span> <span data-ttu-id="41e60-377">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов как место по умолчанию для отчетов.</span><span class="sxs-lookup"><span data-stu-id="41e60-377">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="41e60-378">В поле **Имя**замените имя по умолчанию на «Параметризованный отчет о продажах».</span><span class="sxs-lookup"><span data-stu-id="41e60-378">In **Name**, replace the default name with Parameterized Sales Report.</span></span>  
  
5.  <span data-ttu-id="41e60-379">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="41e60-379">Click **Save**.</span></span>  
  
 <span data-ttu-id="41e60-380">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="41e60-380">The report is saved to the report server.</span></span> <span data-ttu-id="41e60-381">Сервер отчетов, с которым установлено соединение, будет отображен в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="41e60-381">The report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="41e60-382">Next Steps</span><span class="sxs-lookup"><span data-stu-id="41e60-382">Next Steps</span></span>  
 <span data-ttu-id="41e60-383">На этом пошаговое руководство по добавлению параметра в отчет завершается.</span><span class="sxs-lookup"><span data-stu-id="41e60-383">This concludes the walkthrough for how to add a parameter to your report.</span></span> <span data-ttu-id="41e60-384">Дополнительные сведения о параметрах см. в разделе [Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="41e60-384">To learn more about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e60-385">См. также:</span><span class="sxs-lookup"><span data-stu-id="41e60-385">See Also</span></span>  
 <span data-ttu-id="41e60-386">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="41e60-386">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="41e60-387">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="41e60-387">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
