---
title: Учебник. Добавление спарклайна в отчет (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 18c90a36-48bf-4805-a960-2d1e8f00c2dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1bf83810b6c743b977e399864ce2edd514f572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735946"
---
# <a name="tutorial-add-a-sparkline-to-your-report-report-builder"></a><span data-ttu-id="1a036-102">Учебник. Добавление спарклайна в отчет (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="1a036-102">Tutorial: Add a Sparkline to Your Report (Report Builder)</span></span>
  <span data-ttu-id="1a036-103">Этот учебник помогает создать простой табличный отчет на основе образцов данных продаж и добавить спарклайн-график в ячейку таблицы.</span><span class="sxs-lookup"><span data-stu-id="1a036-103">In this tutorial, you create a basic table report based on sample sales data, and then add a sparkline chart to a cell in the table.</span></span>  
  
 <span data-ttu-id="1a036-104">Улучшенная версия отчета, созданного в этом учебнике, доступна в качестве образца отчета в построителе отчетов [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a036-104">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="1a036-105">Дополнительные сведения о загрузке этого и других образцов отчетов см. в разделе [Образцы отчетов построителя отчетов](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="1a036-105">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span> <span data-ttu-id="1a036-106">На следующем рисунке показан образец отчета, похожий на тот, который будет в итоге создан.</span><span class="sxs-lookup"><span data-stu-id="1a036-106">The following illustration shows the sample report similar to the one that you will create.</span></span>  
  
 <span data-ttu-id="1a036-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span><span class="sxs-lookup"><span data-stu-id="1a036-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span></span>  
  
 <span data-ttu-id="1a036-108">Видеоролик [Как создать спарклайн в таблице (видеоматериалы по построителю отчетов)](https://technet.microsoft.com/bi/ff871942.aspx) показывает, как создать подобный отчет со спарклайнами.</span><span class="sxs-lookup"><span data-stu-id="1a036-108">The video [How to: Create a Sparkline in a Table (Report Builder Video)](https://technet.microsoft.com/bi/ff871942.aspx) illustrates how to create a similar report with sparklines.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="1a036-109">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="1a036-109">What You Will Learn</span></span>  
 <span data-ttu-id="1a036-110">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="1a036-110">In this tutorial, you will learn how to do the following:</span></span>  
  
 1. [<span data-ttu-id="1a036-111">Создание табличного отчета</span><span class="sxs-lookup"><span data-stu-id="1a036-111">Create a Report with a Table</span></span>](#CreateTable)  
  
 2. [<span data-ttu-id="1a036-112">Создание запроса в мастере таблиц или матриц</span><span class="sxs-lookup"><span data-stu-id="1a036-112">Create a Query in the Table or Matrix Wizard</span></span>](#Query)  
  
 3. [<span data-ttu-id="1a036-113">Добавление спарклайна в таблицу</span><span class="sxs-lookup"><span data-stu-id="1a036-113">Add a Sparkline to the Table</span></span>](#Sparkline)  
  
 4. [<span data-ttu-id="1a036-114">Выравнивание спарклайнов по вертикали и горизонтали</span><span class="sxs-lookup"><span data-stu-id="1a036-114">Align the Sparklines Vertically and Horizontally</span></span>](#AlignSparklines)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="1a036-115">Другие дополнительные шаги</span><span class="sxs-lookup"><span data-stu-id="1a036-115">Other Optional Steps</span></span>  
 5. [<span data-ttu-id="1a036-116">Форматирование данных в денежном формате</span><span class="sxs-lookup"><span data-stu-id="1a036-116">Format Data as Currency</span></span>](#FormatCurrency)  
  
 6. [<span data-ttu-id="1a036-117">Форматирование данных в формате даты</span><span class="sxs-lookup"><span data-stu-id="1a036-117">Format Data as Dates</span></span>](#FormatDates)  
  
 7. [<span data-ttu-id="1a036-118">Изменение ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="1a036-118">Change Column Widths</span></span>](#Width)  
  
 8. [<span data-ttu-id="1a036-119">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="1a036-119">Add a Report Title</span></span>](#Title)  
  
 9. [<span data-ttu-id="1a036-120">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="1a036-120">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="1a036-121">Предполагаемое время для выполнения заданий данного учебника: 30 минут.</span><span class="sxs-lookup"><span data-stu-id="1a036-121">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a036-122">Требования</span><span class="sxs-lookup"><span data-stu-id="1a036-122">Requirements</span></span>  
 <span data-ttu-id="1a036-123">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="1a036-123">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-report-with-a-table"></a><a name="CreateTable"></a><span data-ttu-id="1a036-124">1. Создание отчета с таблицей</span><span class="sxs-lookup"><span data-stu-id="1a036-124">1. Create a Report with a Table</span></span>  
  
#### <a name="to-create-a-report"></a><span data-ttu-id="1a036-125">Создание отчета</span><span class="sxs-lookup"><span data-stu-id="1a036-125">To create a report</span></span>  
  
1.  <span data-ttu-id="1a036-126">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="1a036-126">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="1a036-127">Откроется диалоговое окно **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="1a036-127">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a036-128">Если диалоговое окно **Начало работы** не отображается, на кнопке **Построитель отчетов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="1a036-128">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="1a036-129">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="1a036-129">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="1a036-130">На панели справа выберите **Мастер таблицы или матрицы**.</span><span class="sxs-lookup"><span data-stu-id="1a036-130">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="1a036-131">На странице **Выбор набора данных** выберите команду **Создать набор данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a036-131">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="1a036-132">Откроется страница **Выберите соединение с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="1a036-132">The **Choose a connection to a data source** page opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a036-133">Для этого учебника не требуется специальных данных. Необходимо только соединение с базой данных [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a036-133">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="1a036-134">Если соединение с источником данных, входящим в список **Соединения с источниками данных**уже имеется, выберите его и переходите к шагу 10.</span><span class="sxs-lookup"><span data-stu-id="1a036-134">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to step 10.</span></span> <span data-ttu-id="1a036-135">Дополнительные сведения см. в разделе [Альтернативные способы создания подключения к данным &#40;построитель отчетов&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1a036-135">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  <span data-ttu-id="1a036-136">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1a036-136">Click **New**.</span></span> <span data-ttu-id="1a036-137">Откроется диалоговое окно **Свойства источника данных** .</span><span class="sxs-lookup"><span data-stu-id="1a036-137">The **Data Source Properties** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="1a036-138">В текстовое поле **Имя**введите имя источника данных: **Продажи продукции**.</span><span class="sxs-lookup"><span data-stu-id="1a036-138">In **Name**, type **Product Sales**, a name for the data source.</span></span>  
  
7.  <span data-ttu-id="1a036-139">Убедитесь, что в поле **Выберите тип соединения**выбран тип **Microsoft SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="1a036-139">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
8.  <span data-ttu-id="1a036-140">В поле **Строка подключения**введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="1a036-140">In **Connection string**, type the following text:</span></span>  
  
     <span data-ttu-id="1a036-141">**Источник данных =\<servername>**</span><span class="sxs-lookup"><span data-stu-id="1a036-141">**Data Source=\<servername>**</span></span>  
  
     <span data-ttu-id="1a036-142">Выражение \<servername>, например Report001, указывает компьютер, на котором установлен экземпляр компонента SQL Server Database Engine.</span><span class="sxs-lookup"><span data-stu-id="1a036-142">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="1a036-143">Поскольку данные отчета не извлекаются из базы данных SQL Server, не нужно указывать имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="1a036-143">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="1a036-144">Для синтаксического анализа запроса используется база данных по умолчанию на указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="1a036-144">The default database on the specified server is used to parse the query.</span></span>  
  
9. <span data-ttu-id="1a036-145">Нажмите кнопку **Учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="1a036-145">Click **Credentials**.</span></span> <span data-ttu-id="1a036-146">Введите учетные данные, необходимые для доступа к внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="1a036-146">Enter the credentials that you need to access the external data source.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="1a036-147">Снова откроется страница **Выбор соединения с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="1a036-147">You are back on the **Choose a connection to a data source** page.</span></span>  
  
11. <span data-ttu-id="1a036-148">Нажмите кнопку **Проверить соединение**, чтобы проверить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="1a036-148">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="1a036-149">Отобразится сообщение «Соединение установлено успешно».</span><span class="sxs-lookup"><span data-stu-id="1a036-149">The message "Connection created successfully" appears.</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="1a036-150">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a036-150">Click **Next**.</span></span>  
  
##  <a name="2-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="1a036-151">2. Создание запроса в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="1a036-151">2. Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="1a036-152">В отчете можно использовать общий набор данных со стандартным запросом или создать внедренный набор данных только для этого отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-152">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="1a036-153">В этом учебнике рассматривается создание внедренного набора данных.</span><span class="sxs-lookup"><span data-stu-id="1a036-153">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a036-154">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="1a036-154">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="1a036-155">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="1a036-155">This makes the query quite long.</span></span> <span data-ttu-id="1a036-156">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="1a036-156">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="1a036-157">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="1a036-157">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="1a036-158">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="1a036-158">To create a query</span></span>  
  
1.  <span data-ttu-id="1a036-159">На странице **Создание запроса** открывается конструктор реляционных запросов.</span><span class="sxs-lookup"><span data-stu-id="1a036-159">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="1a036-160">В этом учебнике будет использоваться текстовый конструктор запросов.</span><span class="sxs-lookup"><span data-stu-id="1a036-160">For this tutorial, you will use the text-based query designer.</span></span>  
  
2.  <span data-ttu-id="1a036-161">Нажмите кнопку **изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="1a036-161">Click **Edit As Text**.</span></span> <span data-ttu-id="1a036-162">Текстовый конструктор запросов отображает панель запросов и панель результатов.</span><span class="sxs-lookup"><span data-stu-id="1a036-162">The text-based query designer displays a query pane and a results pane.</span></span>  
  
3.  <span data-ttu-id="1a036-163">Вставьте в поле [!INCLUDE[tsql](../includes/tsql-md.md)] Запрос **следующий запрос** .</span><span class="sxs-lookup"><span data-stu-id="1a036-163">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Budget Movie-Maker' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Slim Digital' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,'Accessories' as Subcategory,    
       'Budget Movie-Maker' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2010-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Carrying Case' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
4.  <span data-ttu-id="1a036-164">На панели инструментов конструктора запросов нажмите кнопку "Выполнить" (**!**).</span><span class="sxs-lookup"><span data-stu-id="1a036-164">On the query designer toolbar, click Run  (**!**).</span></span>  
  
     <span data-ttu-id="1a036-165">Запрос выполняется и отображает результирующий набор для полей **SalesDate**, **Subcategory**, **Product**, **Sales**и **Quantity**.</span><span class="sxs-lookup"><span data-stu-id="1a036-165">The query runs and displays the result set for the fields **SalesDate**, **Subcategory**, **Product**, **Sales**, and **Quantity**.</span></span>  
  
5.  <span data-ttu-id="1a036-166">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a036-166">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="1a036-167">На странице **Размещение полей** перетащите поле **Sales** в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="1a036-167">On the **Arrange fields** page, drag **Sales** to **Values**.</span></span>  
  
     <span data-ttu-id="1a036-168">Значение поля**Sales** вычисляется агрегатной функцией Sum.</span><span class="sxs-lookup"><span data-stu-id="1a036-168">**Sales** is aggregated by the Sum function.</span></span> <span data-ttu-id="1a036-169">Значение равно [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="1a036-169">The value is [Sum(Sales)].</span></span>  
  
7.  <span data-ttu-id="1a036-170">Перетащите поле **Product** в область **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="1a036-170">Drag **Product** to **Row groups**.</span></span>  
  
8.  <span data-ttu-id="1a036-171">Перетащите поле **SalesDate** в область **Группы столбцов**.</span><span class="sxs-lookup"><span data-stu-id="1a036-171">Drag **SalesDate** to **Column groups**.</span></span>  
  
9. <span data-ttu-id="1a036-172">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a036-172">Click **Next**.</span></span>  
  
10. <span data-ttu-id="1a036-173">На странице **Выбор макета** в разделе **Параметры**убедитесь, что выбран параметр **Показывать подытоги и общие итоги** .</span><span class="sxs-lookup"><span data-stu-id="1a036-173">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="1a036-174">На панели просмотра в мастере отображается таблица с тремя строками.</span><span class="sxs-lookup"><span data-stu-id="1a036-174">The wizard Preview pane displays a table with three rows.</span></span> <span data-ttu-id="1a036-175">При запуске отчета каждая строка отобразится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1a036-175">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="1a036-176">Первая строка отображается один раз для таблицы, в ней будут содержаться заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="1a036-176">The first row will appear once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="1a036-177">Вторая строка повторится один раз для каждого продукта и отобразит название продукта, количество заказа в день и линейный итог.</span><span class="sxs-lookup"><span data-stu-id="1a036-177">The second row will repeat once for each product and display the product name, total per day, and line total.</span></span>  
  
    3.  <span data-ttu-id="1a036-178">Третья строка отобразится один раз для таблицы и будет содержать общие итоги.</span><span class="sxs-lookup"><span data-stu-id="1a036-178">The third row will appear once for the table to display the grand totals.</span></span>  
  
11. <span data-ttu-id="1a036-179">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1a036-179">Click **Next**.</span></span>  
  
12. <span data-ttu-id="1a036-180">На странице **Выбор стиля** панели **Стили** выберите **Сланец**.</span><span class="sxs-lookup"><span data-stu-id="1a036-180">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>  
  
     <span data-ttu-id="1a036-181">На панели предварительного просмотра отобразится образец таблицы с этим стилем.</span><span class="sxs-lookup"><span data-stu-id="1a036-181">The Preview pane displays a sample of the table with that style.</span></span>  
  
13. <span data-ttu-id="1a036-182">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1a036-182">Click **Finish**.</span></span>  
  
14. <span data-ttu-id="1a036-183">Таблица добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="1a036-183">The table is added to the design surface.</span></span> <span data-ttu-id="1a036-184">Таблица содержит три столбца и три строки.</span><span class="sxs-lookup"><span data-stu-id="1a036-184">The table has three columns and three rows.</span></span>  
  
     <span data-ttu-id="1a036-185">Посмотрите на панель группировки.</span><span class="sxs-lookup"><span data-stu-id="1a036-185">Look in the Grouping pane.</span></span> <span data-ttu-id="1a036-186">Если панель группировки не видна, в меню **Вид** выберите пункт **Группирование**.</span><span class="sxs-lookup"><span data-stu-id="1a036-186">If you can't see the Grouping pane, on the **View** menu, click **Grouping**.</span></span> <span data-ttu-id="1a036-187">На панели «Группы строк» показана одна группа строк: **Product**.</span><span class="sxs-lookup"><span data-stu-id="1a036-187">The Row Groups pane shows one row group: **Product**.</span></span> <span data-ttu-id="1a036-188">На панели «Группы строк» показана одна группа столбцов: **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="1a036-188">The Column Groups pane shows one column group: **SalesDate**.</span></span> <span data-ttu-id="1a036-189">Подробные данные — это все данные, которые извлекаются с помощью запроса к набору данных.</span><span class="sxs-lookup"><span data-stu-id="1a036-189">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
15. <span data-ttu-id="1a036-190">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-190">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-add-a-sparkline"></a><a name="Sparkline"></a><span data-ttu-id="1a036-191">3. Добавление спарклайна</span><span class="sxs-lookup"><span data-stu-id="1a036-191">3. Add a Sparkline</span></span>  
  
#### <a name="to-add-a-sparkline-chart-to-a-table"></a><span data-ttu-id="1a036-192">Добавление спарклайн-графика в таблицу</span><span class="sxs-lookup"><span data-stu-id="1a036-192">To add a sparkline chart to a table</span></span>  
  
1.  <span data-ttu-id="1a036-193">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="1a036-193">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="1a036-194">Выберите в таблице столбец Total.</span><span class="sxs-lookup"><span data-stu-id="1a036-194">Select the Total column in your table.</span></span>  
  
3.  <span data-ttu-id="1a036-195">Щелкните правой кнопкой мыши, наведите указатель на пункт **Вставить столбец**и выберите пункт **Слева**.</span><span class="sxs-lookup"><span data-stu-id="1a036-195">Right-click, point to **Insert Column**, and then click **Left**.</span></span>  
  
4.  <span data-ttu-id="1a036-196">В новом столбце щелкните правой кнопкой мыши в строке [Product], выберите вкладку ленты **Вставка** и выберите **Спарклайн**.</span><span class="sxs-lookup"><span data-stu-id="1a036-196">In the new column, right-click in the [Product] row, point to the **Insert** ribbon tab, and then click **Sparkline**.</span></span>  
  
5.  <span data-ttu-id="1a036-197">Убедитесь, что выбран первый спарклайн в строке **Column** , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1a036-197">Make sure the first sparkline in the **Column** row is selected and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="1a036-198">Щелкните спарклайн для отображения панели «Данные диаграммы».</span><span class="sxs-lookup"><span data-stu-id="1a036-198">Click the sparkline to show the Chart Data pane.</span></span>  
  
7.  <span data-ttu-id="1a036-199">Щелкните знак плюса (+) в поле «Значения» и выберите **Sales**.</span><span class="sxs-lookup"><span data-stu-id="1a036-199">Click the plus (+) sign in the Values box, and then click **Sales**.</span></span>  
  
     <span data-ttu-id="1a036-200">Значения в поле **Sales** станут значениями спарклайна.</span><span class="sxs-lookup"><span data-stu-id="1a036-200">The values in the **Sales** field are now the values for the sparkline.</span></span>  
  
8.  <span data-ttu-id="1a036-201">Щелкните знак плюса (+) в поле «Группы категорий» и выберите **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="1a036-201">Click the plus (+) sign in the Category Groups box, and then click **SalesDate**.</span></span>  
  
9. <span data-ttu-id="1a036-202">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-202">Click **Run** to preview your report.</span></span>  
  
     <span data-ttu-id="1a036-203">Обратите внимание, что в каждой строке таблицы есть спарклайн графики, но все они неправильные.</span><span class="sxs-lookup"><span data-stu-id="1a036-203">Note that there are sparkline charts in each row of the table, but they're not correct.</span></span> <span data-ttu-id="1a036-204">Столбцы в диаграммах не соответствуют друг другу.</span><span class="sxs-lookup"><span data-stu-id="1a036-204">The bars in the charts don't line up with each other.</span></span> <span data-ttu-id="1a036-205">Во второй строке данных представлено только четыре столбца, поэтому столбцы шире, чем в первой строке, в которой представлено шесть столбцов.</span><span class="sxs-lookup"><span data-stu-id="1a036-205">There are only four bars in the second row of data, so the bars are wider than the bars in the first row, which has six.</span></span> <span data-ttu-id="1a036-206">Нельзя сравнить значения по каждому продукту в день.</span><span class="sxs-lookup"><span data-stu-id="1a036-206">You can't compare values for each product per day.</span></span> <span data-ttu-id="1a036-207">Для этого они должны стоять вровень друг с другом.</span><span class="sxs-lookup"><span data-stu-id="1a036-207">They need to line up with each other.</span></span>  
  
     <span data-ttu-id="1a036-208">Также обратите внимание, что для каждой строки самый высокий столбец имеет высоту строки.</span><span class="sxs-lookup"><span data-stu-id="1a036-208">Also note that for each row, the tallest bar for that row is the height of the row.</span></span> <span data-ttu-id="1a036-209">Это тоже верно, так как наибольшие значения для каждой строки не равны: наибольшее значение для бюджетного фильма — $10 400, но наибольшее значение для малогабаритного цифрового — $26 576 — больше, чем в два раза больше.</span><span class="sxs-lookup"><span data-stu-id="1a036-209">This is misleading, too, because the largest values for each row are not equal: the largest value for Budget Movie-Maker is $10,400, but the largest value for Slim Digital is $26,576-more than twice as large.</span></span> <span data-ttu-id="1a036-210">Тем не менее наибольшие столбцы в этих двух строках имеют примерно одинаковую высоту.</span><span class="sxs-lookup"><span data-stu-id="1a036-210">And yet the largest bars in those two rows are about the same height.</span></span> <span data-ttu-id="1a036-211">Ее также необходимо привести в соответствие по масштабу с другими спарклайнами.</span><span class="sxs-lookup"><span data-stu-id="1a036-211">That also needs to be made to scale with the other sparklines.</span></span>  
  
     <span data-ttu-id="1a036-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span><span class="sxs-lookup"><span data-stu-id="1a036-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span></span>  
  
##  <a name="4-align-the-sparklines-vertically-and-horizontally"></a><a name="AlignSparklines"></a><span data-ttu-id="1a036-213">4. Выравнивание спарклайнов по вертикали и горизонтали</span><span class="sxs-lookup"><span data-stu-id="1a036-213">4. Align the Sparklines Vertically and Horizontally</span></span>  
 <span data-ttu-id="1a036-214">Спарклайны трудно читать, если они не используют одинаковые измерения.</span><span class="sxs-lookup"><span data-stu-id="1a036-214">The sparklines are hard to read when they don't all use the same measurements.</span></span> <span data-ttu-id="1a036-215">И горизонтальные и вертикальные оси должны совпадать с остальными.</span><span class="sxs-lookup"><span data-stu-id="1a036-215">Both the horizontal and vertical axes for each need to match the rest.</span></span>  
  
#### <a name="to-set-alignment-for-the-sparklines-in-the-table"></a><span data-ttu-id="1a036-216">Выравнивание спарклайнов в таблице</span><span class="sxs-lookup"><span data-stu-id="1a036-216">To set alignment for the sparklines in the table</span></span>  
  
1.  <span data-ttu-id="1a036-217">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="1a036-217">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="1a036-218">Щелкните правой кнопкой мыши спарклайн и выберите пункт **Свойства вертикальной оси**.</span><span class="sxs-lookup"><span data-stu-id="1a036-218">Right-click the sparkline and click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="1a036-219">Установите флажок **Выровнять оси в** .</span><span class="sxs-lookup"><span data-stu-id="1a036-219">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="1a036-220">Tablix1 показан в списке.</span><span class="sxs-lookup"><span data-stu-id="1a036-220">Tablix1 is showing in the list.</span></span> <span data-ttu-id="1a036-221">Это единственный допустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="1a036-221">That is the only option.</span></span> <span data-ttu-id="1a036-222">Параметр устанавливает высоту столбцов в каждом спарклайне относительно других.</span><span class="sxs-lookup"><span data-stu-id="1a036-222">This sets the height of the bars in each sparkline relative to the others.</span></span>  
  
4.  <span data-ttu-id="1a036-223">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1a036-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="1a036-224">Щелкните правой кнопкой мыши спарклайн и выберите пункт **Свойства горизонтальной оси**.</span><span class="sxs-lookup"><span data-stu-id="1a036-224">Right-click the sparkline and click **Horizontal Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="1a036-225">Установите флажок **Выровнять оси в** .</span><span class="sxs-lookup"><span data-stu-id="1a036-225">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="1a036-226">Tablix1 показан в списке.</span><span class="sxs-lookup"><span data-stu-id="1a036-226">Tablix1 is showing in the list.</span></span> <span data-ttu-id="1a036-227">Это единственный допустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="1a036-227">That is the only option.</span></span> <span data-ttu-id="1a036-228">Параметр устанавливает ширину столбцов в каждом спарклайне относительно других.</span><span class="sxs-lookup"><span data-stu-id="1a036-228">This sets the width of the bars in each sparkline relative to the others.</span></span> <span data-ttu-id="1a036-229">Если некоторые из спарклайнов имеют меньше столбцов, чем другие, то на месте отсутствующих данных они будут отображать пустое пространство.</span><span class="sxs-lookup"><span data-stu-id="1a036-229">If some sparklines have fewer bars than others, then those sparklines will have blank spaces for the missing data.</span></span>  
  
7.  <span data-ttu-id="1a036-230">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1a036-230">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="1a036-231">Нажмите кнопку **Выполнить** для повторного предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-231">Click **Run** to preview your report again.</span></span>  
  
 <span data-ttu-id="1a036-232">Обратите внимание, что теперь все столбцы выровнены по отношению к столбцам в других строках.</span><span class="sxs-lookup"><span data-stu-id="1a036-232">Note that all the bars are now aligned with the bars in the other rows.</span></span>  
  
##  <a name="5-optional-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="1a036-233">5. (необязательно) форматирование данных в денежном формате</span><span class="sxs-lookup"><span data-stu-id="1a036-233">5. (Optional) Format Data as Currency</span></span>  
 <span data-ttu-id="1a036-234">По умолчанию сводные данные для поля **Sales (продажи** ) отображаются в виде общего числа.</span><span class="sxs-lookup"><span data-stu-id="1a036-234">By default, the summary data for the **Sales** field displays a general number.</span></span> <span data-ttu-id="1a036-235">Отформатируйте его для представления валюты.</span><span class="sxs-lookup"><span data-stu-id="1a036-235">Format it to display the number as currency.</span></span> <span data-ttu-id="1a036-236">Чтобы форматируемые текстовые поля и текст заполнителей отображался в виде образцов значений, переключайте параметр **Стили заполнителя** .</span><span class="sxs-lookup"><span data-stu-id="1a036-236">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="1a036-237">Форматирование поля валюты</span><span class="sxs-lookup"><span data-stu-id="1a036-237">To format a currency field</span></span>  
  
1.  <span data-ttu-id="1a036-238">Нажмите кнопку **конструктор** , чтобы перейти в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="1a036-238">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="1a036-239">Щелкните ячейку во второй строке (под строкой заголовков столбцов) в столбце **SalesDate** и перетащите указатель мыши вниз, чтобы выбрать все ячейки, содержащие `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="1a036-239">Click the cell in the second row (under the column headings row) in the **SalesDate** column and drag to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="1a036-240">На вкладке **Главная** в группе **Число** нажмите кнопку **Валюта** .</span><span class="sxs-lookup"><span data-stu-id="1a036-240">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="1a036-241">Ячейки изменятся, отображая содержимое в формате валюты.</span><span class="sxs-lookup"><span data-stu-id="1a036-241">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="1a036-242">Если в качестве региональных настроек компьютера выбран "Английский (США)", текстом по умолчанию образца будет [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="1a036-242">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="1a036-243">Если значение валюты не отображается, щелкните ссылку **Стили заполнителя** в группе **Числа** , а затем нажмите кнопку **Образцы значений**.</span><span class="sxs-lookup"><span data-stu-id="1a036-243">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="1a036-244">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-244">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="1a036-245">Сводные значения для столбца **Sales** отображаются в денежном формате.</span><span class="sxs-lookup"><span data-stu-id="1a036-245">The summary values for **Sales** display as currency.</span></span>  
  
##  <a name="6-optional-format-data-as-dates"></a><a name="FormatDates"></a><span data-ttu-id="1a036-246">6. (необязательно) форматирование данных в виде дат</span><span class="sxs-lookup"><span data-stu-id="1a036-246">6. (Optional) Format Data as Dates</span></span>  
 <span data-ttu-id="1a036-247">По умолчанию в поле **SalesDate** отображаются сведения о дате и времени.</span><span class="sxs-lookup"><span data-stu-id="1a036-247">By default, the **SalesDate** field displays both date and time information.</span></span> <span data-ttu-id="1a036-248">Можно отформатировать его таким образом, чтобы отображалась только дата.</span><span class="sxs-lookup"><span data-stu-id="1a036-248">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="1a036-249">Указание форматирования для поля даты в формат по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1a036-249">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="1a036-250">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="1a036-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="1a036-251">Щелкните ячейку, содержащую `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="1a036-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="1a036-252">На ленте, на вкладке **Корневая папка** в группе **Число** в раскрывающемся списке выберите **Дата**.</span><span class="sxs-lookup"><span data-stu-id="1a036-252">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="1a036-253">В ячейке отображается пример даты **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="1a036-253">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="1a036-254">Если дата не отображается, щелкните ссылку **Стили заполнителя** в группе **Числа** , а затем нажмите кнопку **Образцы значений**.</span><span class="sxs-lookup"><span data-stu-id="1a036-254">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="1a036-255">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-255">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1a036-256">Значения **SalesDate** отображаются в формате даты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a036-256">The **SalesDate** values display in the default date format.</span></span>  
  
##  <a name="7-optional-change-column-widths"></a><a name="Width"></a><span data-ttu-id="1a036-257">7. изменение ширины столбцов (необязательно)</span><span class="sxs-lookup"><span data-stu-id="1a036-257">7. (Optional) Change Column Widths</span></span>  
 <span data-ttu-id="1a036-258">По умолчанию в каждой ячейке таблицы есть текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="1a036-258">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="1a036-259">Текстовое поле расширяется вниз, чтобы вместить введенный текст при подготовке страницы к просмотру.</span><span class="sxs-lookup"><span data-stu-id="1a036-259">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="1a036-260">В отчете, готовом для просмотра, каждая строка расширяется по высоте самого высокого текстового поля в строке.</span><span class="sxs-lookup"><span data-stu-id="1a036-260">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="1a036-261">Высота строки в области конструктора не влияет на высоту строки в отчете, готовом для просмотра.</span><span class="sxs-lookup"><span data-stu-id="1a036-261">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="1a036-262">Чтобы уменьшить высоту каждой строки, увеличьте ширину столбца, чтобы ожидаемое содержимое текстовых полей умещалось в одну строку.</span><span class="sxs-lookup"><span data-stu-id="1a036-262">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-columns"></a><span data-ttu-id="1a036-263">Изменение ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="1a036-263">To change the width of columns</span></span>  
  
1.  <span data-ttu-id="1a036-264">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="1a036-264">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="1a036-265">Щелкните таблицу, чтобы сбоку и сверху от нее появились маркеры строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="1a036-265">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="1a036-266">Серые линии, расположенные вдоль верха и стороны таблицы, — это маркеры столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="1a036-266">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="1a036-267">Установите указатель на линии раздела между маркерами столбцов, чтобы курсор принял вид двойной стрелки.</span><span class="sxs-lookup"><span data-stu-id="1a036-267">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="1a036-268">Перетаскиванием установите нужный размер столбцов.</span><span class="sxs-lookup"><span data-stu-id="1a036-268">Drag the columns to the size you want.</span></span> <span data-ttu-id="1a036-269">Например, расширьте столбец **Product** , чтобы название продукта отображалось в одной строке.</span><span class="sxs-lookup"><span data-stu-id="1a036-269">For example, expand the column for **Product** so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="1a036-270">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-270">Click **Run** to preview your report.</span></span>  
  
##  <a name="8-optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="1a036-271">8. (необязательно) Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="1a036-271">8. (Optional) Add a Report Title</span></span>  
 <span data-ttu-id="1a036-272">Заголовок отчета отображается в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-272">A report title appears at the top of the report.</span></span> <span data-ttu-id="1a036-273">Можно поместить заголовок отчета в верхнем колонтитуле или, если в отчете колонтитулы не используются, в текстовом поле в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-273">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="1a036-274">В данном учебнике это текстовое поле автоматически размещается в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="1a036-274">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="1a036-275">Текст можно улучшить, применяя к отдельным символам различные стили шрифтов, размеры и цвета.</span><span class="sxs-lookup"><span data-stu-id="1a036-275">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="1a036-276">Дополнительные сведения см. в разделе [Форматирование текста в текстовом поле &#40;построитель отчетов и службы SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1a036-276">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="1a036-277">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="1a036-277">To add a report title</span></span>  
  
1.  <span data-ttu-id="1a036-278">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="1a036-278">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="1a036-279">Введите фразу **Product Sales**и щелкните вне текстового поля.</span><span class="sxs-lookup"><span data-stu-id="1a036-279">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="1a036-280">Щелкните правой кнопкой мыши текстовое поле **Продажи товаров** и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="1a036-280">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="1a036-281">В диалоговом окне **Свойства текстового поля** нажмите кнопку **Шрифт**.</span><span class="sxs-lookup"><span data-stu-id="1a036-281">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="1a036-282">В списке **Размер** выберите **18пт**.</span><span class="sxs-lookup"><span data-stu-id="1a036-282">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="1a036-283">В списке **Цвет** выберите **Каштановый**.</span><span class="sxs-lookup"><span data-stu-id="1a036-283">In the **Color** list, select **Maroon**.</span></span>  
  
7.  <span data-ttu-id="1a036-284">Выберите **Полужирное**начертание.</span><span class="sxs-lookup"><span data-stu-id="1a036-284">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="1a036-285">9. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="1a036-285">9. Save the Report</span></span>  
 <span data-ttu-id="1a036-286">Сохраните отчет на сервере отчетов или на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="1a036-286">Save the report to a report server or your computer.</span></span> <span data-ttu-id="1a036-287">Если не сохранить отчет на сервере отчетов, некоторые функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , в том числе элементы отчета и вложенные отчеты, будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="1a036-287">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="1a036-288">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="1a036-288">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="1a036-289">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="1a036-289">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="1a036-290">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="1a036-290">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="1a036-291">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="1a036-291">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="1a036-292">Появится сообщение «Соединение с сервером отчетов».</span><span class="sxs-lookup"><span data-stu-id="1a036-292">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="1a036-293">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов как место по умолчанию для отчетов.</span><span class="sxs-lookup"><span data-stu-id="1a036-293">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="1a036-294">В поле **Имя**замените имя по умолчанию фразой **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="1a036-294">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="1a036-295">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1a036-295">Click **Save**.</span></span>  
  
 <span data-ttu-id="1a036-296">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="1a036-296">The report is saved to the report server.</span></span> <span data-ttu-id="1a036-297">Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="1a036-297">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="1a036-298">Сохранение отчета на компьютере</span><span class="sxs-lookup"><span data-stu-id="1a036-298">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="1a036-299">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="1a036-299">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="1a036-300">Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="1a036-300">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="1a036-301">В поле **Имя**замените имя по умолчанию фразой **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="1a036-301">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="1a036-302">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1a036-302">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1a036-303">Next Steps</span><span class="sxs-lookup"><span data-stu-id="1a036-303">Next Steps</span></span>  
 <span data-ttu-id="1a036-304">На этом заканчивается учебник по созданию табличного отчета со спарклайн графиками.</span><span class="sxs-lookup"><span data-stu-id="1a036-304">This concludes the tutorial for creating a table report with sparkline charts.</span></span> <span data-ttu-id="1a036-305">Дополнительные сведения о спарклайнах см. в разделе [Спарклайны и гистограммы (построитель отчетов и службы SSRS)](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1a036-305">For more information about sparklines, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a036-306">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a036-306">See Also</span></span>  
 <span data-ttu-id="1a036-307">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="1a036-307">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="1a036-308">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1a036-308">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
