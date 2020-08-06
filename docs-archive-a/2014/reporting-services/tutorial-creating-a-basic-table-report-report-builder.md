---
title: Руководство по Создание простого табличного отчета (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d9e30521-f8ae-4c45-89c3-d40727f622f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3587e2a53e2b09dd347a2733875eafd708b8a05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656970"
---
# <a name="tutorial-creating-a-basic-table-report-report-builder"></a><span data-ttu-id="523e1-102">Руководство по Создание простого табличного отчета (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="523e1-102">Tutorial: Creating a Basic Table Report (Report Builder)</span></span>
  <span data-ttu-id="523e1-103">Это учебник поможет создать простой табличный отчет на основе образца данных по продажам.</span><span class="sxs-lookup"><span data-stu-id="523e1-103">This tutorial teaches you to create a basic table report based on sample sales data.</span></span> <span data-ttu-id="523e1-104">На приведенной ниже иллюстрации показан отчет, который предстоит создать.</span><span class="sxs-lookup"><span data-stu-id="523e1-104">The following illustration shows the report you will create.</span></span>  
  
 <span data-ttu-id="523e1-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="523e1-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="523e1-106">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="523e1-106">What You Will Learn</span></span>  
 <span data-ttu-id="523e1-107">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="523e1-107">In this tutorial, you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="523e1-108">Создание нового отчета, начиная со страницы «Приступая к работе»</span><span class="sxs-lookup"><span data-stu-id="523e1-108">Create a New Report from Getting Started</span></span>](#CreateTable)  
  
    1.  [<span data-ttu-id="523e1-109">Указание подключения к данным в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-109">Specify a Data Connection in the Table Wizard</span></span>](#DataConnection)  
  
    2.  [<span data-ttu-id="523e1-110">Создание запроса в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-110">Create a Query in the Table Wizard</span></span>](#Query)  
  
    3.  [<span data-ttu-id="523e1-111">Организация данных в группы в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-111">Organize Data into Groups in the Table Wizard</span></span>](#Groups)  
  
    4.  [<span data-ttu-id="523e1-112">Добавление строк подытога и итога в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-112">Add Subtotal and Total Rows in the Table Wizard</span></span>](#Subtotals)  
  
    5.  [<span data-ttu-id="523e1-113">Выбор стиля в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-113">Choose a Style in the Table Wizard</span></span>](#Style)  
  
2.  [<span data-ttu-id="523e1-114">Форматирование данных в денежном формате</span><span class="sxs-lookup"><span data-stu-id="523e1-114">Format Data as Currency</span></span>](#FormatCurrency)  
  
3.  [<span data-ttu-id="523e1-115">Форматирование данных в формат даты</span><span class="sxs-lookup"><span data-stu-id="523e1-115">Format Data as Date</span></span>](#FormatDate)  
  
4.  [<span data-ttu-id="523e1-116">Изменение ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="523e1-116">Change Column Widths</span></span>](#Width)  
  
5.  [<span data-ttu-id="523e1-117">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-117">Add a Report Title</span></span>](#Title)  
  
6.  [<span data-ttu-id="523e1-118">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-118">Save the Report</span></span>](#Save)  
  
7.  [<span data-ttu-id="523e1-119">Экспорт отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-119">Export the Report</span></span>](#Export)  
  
 <span data-ttu-id="523e1-120">Предполагаемое время для выполнения заданий данного учебника: 20 минут</span><span class="sxs-lookup"><span data-stu-id="523e1-120">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="523e1-121">Требования</span><span class="sxs-lookup"><span data-stu-id="523e1-121">Requirements</span></span>  
 <span data-ttu-id="523e1-122">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="523e1-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-new-report-from-getting-started"></a><a name="CreateTable"></a><span data-ttu-id="523e1-123">1. Создание нового отчета на основе начало работы</span><span class="sxs-lookup"><span data-stu-id="523e1-123">1. Create a New Report from Getting Started</span></span>  
 <span data-ttu-id="523e1-124">Создайте табличный отчет из диалогового окна **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="523e1-124">Create a table report from the **Getting Started** dialog box.</span></span> <span data-ttu-id="523e1-125">Имеется два режима: конструктор отчетов и конструктор общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-125">There are two modes: report design and shared dataset design.</span></span> <span data-ttu-id="523e1-126">В режиме конструктора отчетов данные задаются в области данных отчета, а макет отчета — в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="523e1-126">In report design mode, you specify data in the Report Data pane and the report layout on the design surface.</span></span> <span data-ttu-id="523e1-127">В режиме конструктора общего набора данных создаются запросы к наборам данных для совместного использования.</span><span class="sxs-lookup"><span data-stu-id="523e1-127">In shared dataset design mode, you create dataset queries to share with others.</span></span> <span data-ttu-id="523e1-128">В этом учебнике будет использоваться режим конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="523e1-128">In this tutorial, you will be using report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="523e1-129">Создание нового отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-129">To create a new report</span></span>  
  
1.  <span data-ttu-id="523e1-130">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="523e1-130">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="523e1-131">Откроется диалоговое окно **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="523e1-131">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="523e1-132">Если диалоговое окно **Начало работы** не отображается, на кнопке **Построитель отчетов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="523e1-132">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="523e1-133">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="523e1-133">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="523e1-134">Убедитесь в том, что на панели справа выбран **Мастер таблицы или матрицы** .</span><span class="sxs-lookup"><span data-stu-id="523e1-134">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection-in-the-table-wizard"></a><a name="DataConnection"></a><span data-ttu-id="523e1-135">SR1a.</span><span class="sxs-lookup"><span data-stu-id="523e1-135">1a.</span></span> <span data-ttu-id="523e1-136">Указание подключения к данным в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-136">Specify a Data Connection in the Table Wizard</span></span>  
 <span data-ttu-id="523e1-137">Подключение к данным содержит сведения, необходимые для подключения к внешнему источнику данных, например к базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="523e1-137">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="523e1-138">Обычно сведения о соединении и учетные данные, которые будут использоваться при соединении с источником данных, можно получить у владельца источника данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-138">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span> <span data-ttu-id="523e1-139">Чтобы указать подключение к данным, можно воспользоваться общим источником данных с сервера отчетов или создать внедренный источник данных, используемый только в этом отчете.</span><span class="sxs-lookup"><span data-stu-id="523e1-139">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span>  
  
 <span data-ttu-id="523e1-140">В этом учебнике используется внедренный источник данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-140">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="523e1-141">Дополнительные сведения об использовании общих источников данных см. в разделе [Альтернативные способы создания подключения к данным &#40;построитель отчетов&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="523e1-141">To learn more about using a shared data sources, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="523e1-142">Создание внедренного источника данных</span><span class="sxs-lookup"><span data-stu-id="523e1-142">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="523e1-143">На странице **Выбор набора данных** выберите команду **Создать набор данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="523e1-143">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="523e1-144">Откроется страница **Выберите соединение с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="523e1-144">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="523e1-145">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="523e1-145">Click **New**.</span></span> <span data-ttu-id="523e1-146">Откроется диалоговое окно **Свойства источника данных** .</span><span class="sxs-lookup"><span data-stu-id="523e1-146">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="523e1-147">В поле **имя**введите **продажи продукта** имя для источника данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-147">In **Name**, type **Product Sales** a name for the data source.</span></span>  
  
4.  <span data-ttu-id="523e1-148">Убедитесь, что в поле **Выберите тип соединения**выбран тип **Microsoft SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="523e1-148">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
5.  <span data-ttu-id="523e1-149">В поле **строка подключения**введите следующий текст, где *\<servername>* — имя экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="523e1-149">In **Connection string**, type the following text, where *\<servername>* is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
    ```  
    Data Source=<servername>  
    ```  
  
     <span data-ttu-id="523e1-150">Поскольку используется запрос, содержащий данные, а не извлекающий данные из базы, строка подключения не включает имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-150">Because you will use a query that contains the data instead of retrieving the data from a database, the connection string does not include the database name.</span></span> <span data-ttu-id="523e1-151">Дополнительные сведения см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="523e1-151">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
6.  <span data-ttu-id="523e1-152">Нажмите кнопку **Учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="523e1-152">Click **Credentials**.</span></span> <span data-ttu-id="523e1-153">Введите учетные данные, необходимые для доступа к внешнему источнику данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-153">Enter the credentials that you need to access the external data source.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="523e1-154">Снова откроется страница **Выбор соединения с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="523e1-154">You are back on the **Choose a connection to a data source** page.</span></span>  
  
8.  <span data-ttu-id="523e1-155">Нажмите кнопку **Проверить соединение**, чтобы проверить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-155">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="523e1-156">Отобразится сообщение «Соединение установлено успешно».</span><span class="sxs-lookup"><span data-stu-id="523e1-156">The message "Connection created successfully" appears.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="523e1-157">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="523e1-157">Click **Next**.</span></span>  
  
##  <a name="1b-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="523e1-158">1b.</span><span class="sxs-lookup"><span data-stu-id="523e1-158">1b.</span></span> <span data-ttu-id="523e1-159">Создание запроса в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-159">Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="523e1-160">В отчете можно использовать общий набор данных со стандартным запросом или создать внедренный набор данных только для этого отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-160">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="523e1-161">В этом учебнике рассматривается создание внедренного набора данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-161">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="523e1-162">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="523e1-162">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="523e1-163">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="523e1-163">This makes the query quite long.</span></span> <span data-ttu-id="523e1-164">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="523e1-164">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="523e1-165">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="523e1-165">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="523e1-166">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="523e1-166">To create a query</span></span>  
  
1.  <span data-ttu-id="523e1-167">На странице **Создание запроса** открывается конструктор реляционных запросов.</span><span class="sxs-lookup"><span data-stu-id="523e1-167">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="523e1-168">В этом учебнике будет использоваться текстовый конструктор запросов.</span><span class="sxs-lookup"><span data-stu-id="523e1-168">For this tutorial, you will use the text-based query designer.</span></span>  
  
     <span data-ttu-id="523e1-169">Нажмите кнопку **изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="523e1-169">Click **Edit As Text**.</span></span> <span data-ttu-id="523e1-170">Текстовый конструктор запросов отображает панель запросов и панель результатов.</span><span class="sxs-lookup"><span data-stu-id="523e1-170">The text-based query designer displays a query pane and a results pane.</span></span>  
  
2.  <span data-ttu-id="523e1-171">Вставьте в поле [!INCLUDE[tsql](../includes/tsql-md.md)] Запрос **следующий запрос** .</span><span class="sxs-lookup"><span data-stu-id="523e1-171">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(9924.60 AS money) AS Sales, 68 as Quantity  
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
  
3.  <span data-ttu-id="523e1-172">На панели инструментов конструктора запросов нажмите кнопку **выполнить** (**!**).</span><span class="sxs-lookup"><span data-stu-id="523e1-172">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="523e1-173">Запрос выполняется и отображает результирующий набор для полей SalesDate, Subcategory, Product, Sales и Quantity.</span><span class="sxs-lookup"><span data-stu-id="523e1-173">The query runs and displays the result set for the fields SalesDate, Subcategory, Product, Sales, and Quantity.</span></span>  
  
     <span data-ttu-id="523e1-174">В результирующем наборе столбцам присваиваются заголовки в соответствии с именами в запросе.</span><span class="sxs-lookup"><span data-stu-id="523e1-174">In the result set, the column headings are based on the names in the query.</span></span> <span data-ttu-id="523e1-175">В наборе данных имена полей основываются на именах столбцов и сохраняются в отчете.</span><span class="sxs-lookup"><span data-stu-id="523e1-175">In the dataset, the column headings become the field names, and are saved in the report.</span></span> <span data-ttu-id="523e1-176">После завершения мастера можно просмотреть коллекцию полей набора данных в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-176">After you complete the wizard, you can use the Report Data pane to view the collection of dataset fields.</span></span>  
  
4.  <span data-ttu-id="523e1-177">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="523e1-177">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups-in-the-table-wizard"></a><a name="Groups"></a><span data-ttu-id="523e1-178">1C.</span><span class="sxs-lookup"><span data-stu-id="523e1-178">1c.</span></span> <span data-ttu-id="523e1-179">Организация данных в группы в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-179">Organize Data into Groups in the Table Wizard</span></span>  
 <span data-ttu-id="523e1-180">При выборе полей для группирования создается таблица со строками и столбцами, отображающими подробные и агрегированные данные.</span><span class="sxs-lookup"><span data-stu-id="523e1-180">When you select fields to group on, you design a table that has rows and columns that display detail data and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="523e1-181">Организация данных в группы</span><span class="sxs-lookup"><span data-stu-id="523e1-181">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="523e1-182">На странице **Размещение полей** перетащите элемент Product в область **значения**.</span><span class="sxs-lookup"><span data-stu-id="523e1-182">On the **Arrange fields** page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="523e1-183">Перетащите поле "Количество" в область **Значения** и поместите ниже поля "Продукт".</span><span class="sxs-lookup"><span data-stu-id="523e1-183">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="523e1-184">Значение поля Quantity автоматически вычисляется с помощью функции Sum, агрегатной функции по умолчанию для числовых полей.</span><span class="sxs-lookup"><span data-stu-id="523e1-184">Quantity is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="523e1-185">Значение вычисляется по формуле [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="523e1-185">The value is [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="523e1-186">Доступные агрегатные функции можно просмотреть в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="523e1-186">You can open the drop-down list to view the other aggregate functions available.</span></span> <span data-ttu-id="523e1-187">Не изменяйте агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="523e1-187">Do not change the aggregate function.</span></span>  
  
3.  <span data-ttu-id="523e1-188">Перетащите поле Sales в область **Значения** и поместите его ниже поля [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="523e1-188">Drag Sales to **Values** and place below [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="523e1-189">Значение поля Sales вычисляется агрегатной функцией Sum.</span><span class="sxs-lookup"><span data-stu-id="523e1-189">Sales is aggregated by the Sum function.</span></span> <span data-ttu-id="523e1-190">Значение равно [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="523e1-190">The value is [Sum(Sales)].</span></span>  
  
     <span data-ttu-id="523e1-191">Шаги 1, 2 и 3 задают данные, отображаемые в таблице.</span><span class="sxs-lookup"><span data-stu-id="523e1-191">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="523e1-192">Перетащите поле SalesDate в область **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="523e1-192">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="523e1-193">Перетащите поле "Подкатегория" в область **Группы строк** и поместите его ниже поля SalesDate.</span><span class="sxs-lookup"><span data-stu-id="523e1-193">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="523e1-194">Шаги 4 и 5 организуют значения полей сначала по дате, а потом по подкатегории продукта для данной даты.</span><span class="sxs-lookup"><span data-stu-id="523e1-194">Steps 4 and 5 organize the values for the fields first by date, and then by product subcategory for that date.</span></span>  
  
6.  <span data-ttu-id="523e1-195">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="523e1-195">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotal-and-total-rows-in-the-table-wizard"></a><a name="Subtotals"></a><span data-ttu-id="523e1-196">1д.</span><span class="sxs-lookup"><span data-stu-id="523e1-196">1d.</span></span> <span data-ttu-id="523e1-197">Добавление строк подытога и итога в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-197">Add Subtotal and Total Rows in the Table Wizard</span></span>  
 <span data-ttu-id="523e1-198">После создания групп можно добавить и отформатировать строки, в которых будут отображаться значения агрегатной обработки полей.</span><span class="sxs-lookup"><span data-stu-id="523e1-198">After you create groups, you can add and format rows on which to display aggregate values for the fields.</span></span> <span data-ttu-id="523e1-199">Можно выбрать, следует ли показывать все данные или позволить пользователю сворачивать и разворачивать сгруппированные данные интерактивно.</span><span class="sxs-lookup"><span data-stu-id="523e1-199">You can choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="523e1-200">Добавление подытогов и итогов</span><span class="sxs-lookup"><span data-stu-id="523e1-200">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="523e1-201">На странице **Выбор макета** в разделе **Параметры**убедитесь, что выбран параметр **Показывать подытоги и общие итоги** .</span><span class="sxs-lookup"><span data-stu-id="523e1-201">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
2.  <span data-ttu-id="523e1-202">Убедитесь в том, что выбран параметр **Заблокированный, подытог ниже** .</span><span class="sxs-lookup"><span data-stu-id="523e1-202">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
     <span data-ttu-id="523e1-203">На панели просмотра в мастере отображается таблица с пятью строками.</span><span class="sxs-lookup"><span data-stu-id="523e1-203">The wizard Preview pane displays a table with five rows.</span></span> <span data-ttu-id="523e1-204">При запуске отчета каждая строка отобразится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="523e1-204">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="523e1-205">Первая строка повторится один раз для таблицы, чтобы отобразить заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="523e1-205">The first row will repeat once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="523e1-206">Вторая строка повторится один раз для каждого элемента строки в заказе на продажу и отобразит название продукта, количество заказа и линейный итог.</span><span class="sxs-lookup"><span data-stu-id="523e1-206">The second row will repeat once for each line item in the sales order and display the product name, order quantity, and line total.</span></span>  
  
    3.  <span data-ttu-id="523e1-207">Третья строка повторится один раз для каждого заказа на продажу и отобразит подытоги для каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="523e1-207">The third row will repeat once for each sales order to display subtotals per order.</span></span>  
  
    4.  <span data-ttu-id="523e1-208">Четвертая строка повторится один раз для каждой даты заказа и отобразит подытоги для каждого дня.</span><span class="sxs-lookup"><span data-stu-id="523e1-208">The fourth row will repeat once for each order date to display the subtotals per day.</span></span>  
  
    5.  <span data-ttu-id="523e1-209">Пятая строка повторится один раз для таблицы и отобразит итоговые суммы.</span><span class="sxs-lookup"><span data-stu-id="523e1-209">The fifth row will repeat once for the table to display the grand totals.</span></span>  
  
3.  <span data-ttu-id="523e1-210">Снимите флажок **Развернуть или свернуть группы**.</span><span class="sxs-lookup"><span data-stu-id="523e1-210">Clear the option **Expand/collapse groups**.</span></span> <span data-ttu-id="523e1-211">В описываемом здесь отчете не используется функция углубленной детализации, которая позволяет пользователю разворачивать родительскую групповую иерархию, чтобы отобразить строки дочерней группы и строки подробностей.</span><span class="sxs-lookup"><span data-stu-id="523e1-211">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
4.  <span data-ttu-id="523e1-212">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="523e1-212">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style-in-the-table-wizard"></a><a name="Style"></a><span data-ttu-id="523e1-213">1E.</span><span class="sxs-lookup"><span data-stu-id="523e1-213">1e.</span></span> <span data-ttu-id="523e1-214">Выбор стиля в мастере таблиц</span><span class="sxs-lookup"><span data-stu-id="523e1-214">Choose a Style in the Table Wizard</span></span>  
 <span data-ttu-id="523e1-215">Стиль задает стиль шрифта, набор цветов и стиль границы.</span><span class="sxs-lookup"><span data-stu-id="523e1-215">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-table-style"></a><span data-ttu-id="523e1-216">Задание стиля таблицы</span><span class="sxs-lookup"><span data-stu-id="523e1-216">To specify a table style</span></span>  
  
1.  <span data-ttu-id="523e1-217">На странице **Выбор стиля** на панели Стили выберите океанские.</span><span class="sxs-lookup"><span data-stu-id="523e1-217">On the **Choose a Style** page, in the Styles pane, select Ocean.</span></span>  
  
     <span data-ttu-id="523e1-218">На панели предварительного просмотра отобразится образец таблицы с этим стилем.</span><span class="sxs-lookup"><span data-stu-id="523e1-218">The Preview pane displays a sample of the table with that style.</span></span>  
  
2.  <span data-ttu-id="523e1-219">При желании можно выбрать другие стили, чтобы увидеть таблицу, оформленную в этих стилях.</span><span class="sxs-lookup"><span data-stu-id="523e1-219">Optionally, click the other styles to see the sample with them applied.</span></span>  
  
3.  <span data-ttu-id="523e1-220">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="523e1-220">Click **Finish**.</span></span>  
  
 <span data-ttu-id="523e1-221">Таблица добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="523e1-221">The table is added to the design surface.</span></span> <span data-ttu-id="523e1-222">В таблице содержится 5 столбцов и 5 строк.</span><span class="sxs-lookup"><span data-stu-id="523e1-222">The table has 5 columns and 5 rows.</span></span> <span data-ttu-id="523e1-223">Панель "Группы строк" содержит три группы строк: SalesDate, Subcategory и Details.</span><span class="sxs-lookup"><span data-stu-id="523e1-223">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="523e1-224">Подробные данные — это все данные, которые извлекаются с помощью запроса к набору данных.</span><span class="sxs-lookup"><span data-stu-id="523e1-224">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="523e1-225">2. Форматирование данных в денежном формате</span><span class="sxs-lookup"><span data-stu-id="523e1-225">2. Format Data as Currency</span></span>  
 <span data-ttu-id="523e1-226">По умолчанию сводные данные поля Sales отображаются в виде числа с общим форматом.</span><span class="sxs-lookup"><span data-stu-id="523e1-226">By default, the summary data for the Sales field displays a general number.</span></span> <span data-ttu-id="523e1-227">Отформатируйте его для представления валюты.</span><span class="sxs-lookup"><span data-stu-id="523e1-227">Format it to display the number as currency.</span></span> <span data-ttu-id="523e1-228">Чтобы форматируемые текстовые поля и текст заполнителей отображался в виде образцов значений, переключайте параметр **Стили заполнителя** .</span><span class="sxs-lookup"><span data-stu-id="523e1-228">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="523e1-229">Форматирование поля валюты</span><span class="sxs-lookup"><span data-stu-id="523e1-229">To format a currency field</span></span>  
  
1.  <span data-ttu-id="523e1-230">Нажмите кнопку **конструктор** , чтобы перейти в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="523e1-230">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="523e1-231">Щелкните ячейку во второй строке (под строкой заголовков столбцов) в столбце Sales и перетащите указатель мыши вниз, чтобы выбрать все ячейки, содержащие `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="523e1-231">Click the cell in the second row (under the column headings row) in the Sales column and drag down to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="523e1-232">На вкладке **Главная** в группе **Число** нажмите кнопку **Валюта** .</span><span class="sxs-lookup"><span data-stu-id="523e1-232">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="523e1-233">Ячейки изменятся, отображая содержимое в формате валюты.</span><span class="sxs-lookup"><span data-stu-id="523e1-233">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="523e1-234">Если в качестве региональных настроек компьютера выбран "Английский (США)", текстом по умолчанию образца будет [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="523e1-234">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="523e1-235">Если значение валюты не отображается, щелкните ссылку **Стили заполнителя** в группе **Числа** , а затем нажмите кнопку **Образцы значений**.</span><span class="sxs-lookup"><span data-stu-id="523e1-235">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="523e1-236">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-236">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="523e1-237">Сводные значения для столбца Sales отображаются в денежном формате.</span><span class="sxs-lookup"><span data-stu-id="523e1-237">The summary values for Sales display as currency.</span></span>  
  
##  <a name="3-format-data-as-date"></a><a name="FormatDate"></a><span data-ttu-id="523e1-238">3. Форматирование данных в формате даты</span><span class="sxs-lookup"><span data-stu-id="523e1-238">3. Format Data as Date</span></span>  
 <span data-ttu-id="523e1-239">По умолчанию в поле SalesDate отображаются дата и время.</span><span class="sxs-lookup"><span data-stu-id="523e1-239">By default, the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="523e1-240">Можно отформатировать его таким образом, чтобы отображалась только дата.</span><span class="sxs-lookup"><span data-stu-id="523e1-240">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="523e1-241">Указание форматирования для поля даты в формат по умолчанию</span><span class="sxs-lookup"><span data-stu-id="523e1-241">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="523e1-242">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="523e1-242">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="523e1-243">Щелкните ячейку, содержащую `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="523e1-243">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="523e1-244">На ленте, на вкладке **Корневая папка** в группе **Число** в раскрывающемся списке выберите **Дата**.</span><span class="sxs-lookup"><span data-stu-id="523e1-244">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="523e1-245">В ячейке отображается пример даты **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="523e1-245">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="523e1-246">Если дата не отображается, щелкните ссылку **Стили заполнителя** в группе **Числа** , а затем нажмите кнопку **Образцы значений**.</span><span class="sxs-lookup"><span data-stu-id="523e1-246">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="523e1-247">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-247">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="523e1-248">Значения SalesDate отображаются в формате даты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="523e1-248">The SalesDate values display in the default date format.</span></span>  
  
#### <a name="to-change-the-date-format-to-a-custom-format"></a><span data-ttu-id="523e1-249">Замена формата даты на пользовательский формат</span><span class="sxs-lookup"><span data-stu-id="523e1-249">To change the date format to a custom format</span></span>  
  
1.  <span data-ttu-id="523e1-250">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="523e1-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="523e1-251">Щелкните ячейку, содержащую `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="523e1-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="523e1-252">На вкладке **Главная** в группе **число** щелкните средство запуска диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="523e1-252">On the **Home** tab, in the **Number** group, click the dialog box launcher.</span></span>  
  
     <span data-ttu-id="523e1-253">Кнопка запуска — это маленькая стрелка в правом углу группы.</span><span class="sxs-lookup"><span data-stu-id="523e1-253">The launcher is the small arrow in the right-hand corner of the group.</span></span> <span data-ttu-id="523e1-254">Откроется диалоговое окно **Свойства текстового поля** .</span><span class="sxs-lookup"><span data-stu-id="523e1-254">The **Text Box Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="523e1-255">Убедитесь в том, что на панели категорий выбран пункт **Дата** .</span><span class="sxs-lookup"><span data-stu-id="523e1-255">In the Category pane, verify that **Date** is selected.</span></span>  
  
5.  <span data-ttu-id="523e1-256">На панели **Тип** выберите **31 января 2000 года**.</span><span class="sxs-lookup"><span data-stu-id="523e1-256">In the **Type** pane, select **January 31, 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="523e1-257">В ячейке отобразится пример даты **[31 января 2000 года]**.</span><span class="sxs-lookup"><span data-stu-id="523e1-257">The cell displays the example date **[January 31, 2000]**.</span></span>  
  
7.  <span data-ttu-id="523e1-258">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-258">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="523e1-259">Значение SalesDate отображается с названием месяца вместо его номера.</span><span class="sxs-lookup"><span data-stu-id="523e1-259">The SalesDate value displays with the name of the month instead of the number for the month.</span></span>  
  
##  <a name="4-change-column-widths"></a><a name="Width"></a><span data-ttu-id="523e1-260">4. изменение ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="523e1-260">4. Change Column Widths</span></span>  
 <span data-ttu-id="523e1-261">По умолчанию в каждой ячейке таблицы есть текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="523e1-261">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="523e1-262">Текстовое поле расширяется вниз, чтобы вместить введенный текст при подготовке страницы к просмотру.</span><span class="sxs-lookup"><span data-stu-id="523e1-262">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="523e1-263">В отчете, готовом для просмотра, каждая строка расширяется по высоте самого высокого текстового поля в строке.</span><span class="sxs-lookup"><span data-stu-id="523e1-263">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="523e1-264">Высота строки в области конструктора не влияет на высоту строки в отчете, готовом для просмотра.</span><span class="sxs-lookup"><span data-stu-id="523e1-264">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="523e1-265">Чтобы уменьшить высоту каждой строки, увеличьте ширину столбца, чтобы ожидаемое содержимое текстовых полей умещалось в одну строку.</span><span class="sxs-lookup"><span data-stu-id="523e1-265">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-table-columns"></a><span data-ttu-id="523e1-266">Изменение ширины столбцов таблицы</span><span class="sxs-lookup"><span data-stu-id="523e1-266">To change the width of table columns</span></span>  
  
1.  <span data-ttu-id="523e1-267">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="523e1-267">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="523e1-268">Щелкните таблицу, чтобы сбоку и сверху от нее появились маркеры строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="523e1-268">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="523e1-269">Серые линии, расположенные вдоль верха и стороны таблицы, — это маркеры столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="523e1-269">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="523e1-270">Установите указатель на линии раздела между маркерами столбцов, чтобы курсор принял вид двойной стрелки.</span><span class="sxs-lookup"><span data-stu-id="523e1-270">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="523e1-271">Перетаскиванием установите нужный размер столбцов.</span><span class="sxs-lookup"><span data-stu-id="523e1-271">Drag the columns to the size you want.</span></span> <span data-ttu-id="523e1-272">Например, расширьте столбец Product, чтобы название продукта отображалось в одной строке.</span><span class="sxs-lookup"><span data-stu-id="523e1-272">For example, expand the column for Product so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="523e1-273">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-273">Click **Run** to preview your report.</span></span>  
  
##  <a name="5-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="523e1-274">5. Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-274">5. Add a Report Title</span></span>  
 <span data-ttu-id="523e1-275">Заголовок отчета отображается в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-275">A report title appears at the top of the report.</span></span> <span data-ttu-id="523e1-276">Можно поместить заголовок отчета в верхнем колонтитуле или, если в отчете колонтитулы не используются, в текстовом поле в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-276">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="523e1-277">В данном учебнике это текстовое поле автоматически размещается в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-277">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="523e1-278">Текст можно улучшить, применяя к отдельным символам различные стили шрифтов, размеры и цвета.</span><span class="sxs-lookup"><span data-stu-id="523e1-278">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="523e1-279">Дополнительные сведения см. в разделе [Форматирование текста в текстовом поле &#40;построитель отчетов и службы SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="523e1-279">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="523e1-280">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-280">To add a report title</span></span>  
  
1.  <span data-ttu-id="523e1-281">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="523e1-281">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="523e1-282">Введите фразу **Product Sales**и щелкните вне текстового поля.</span><span class="sxs-lookup"><span data-stu-id="523e1-282">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="523e1-283">Щелкните правой кнопкой мыши текстовое поле **Продажи товаров** и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="523e1-283">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="523e1-284">В диалоговом окне **Свойства текстового поля** нажмите кнопку **Шрифт**.</span><span class="sxs-lookup"><span data-stu-id="523e1-284">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="523e1-285">В списке **Размер** выберите **18пт**.</span><span class="sxs-lookup"><span data-stu-id="523e1-285">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="523e1-286">В списке **Цвет** выберите **Васильковый**.</span><span class="sxs-lookup"><span data-stu-id="523e1-286">In the **Color** list, select **Cornflower Blue**.</span></span>  
  
7.  <span data-ttu-id="523e1-287">Выберите **Полужирное**начертание.</span><span class="sxs-lookup"><span data-stu-id="523e1-287">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report"></a><a name="Save"></a><span data-ttu-id="523e1-288">6. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-288">6. Save the Report</span></span>  
 <span data-ttu-id="523e1-289">Сохраните отчет на сервере отчетов или на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="523e1-289">Save the report to a report server or your computer.</span></span> <span data-ttu-id="523e1-290">Если не сохранить отчет на сервере отчетов, некоторые функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , в том числе элементы отчета и вложенные отчеты, будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="523e1-290">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="523e1-291">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="523e1-291">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="523e1-292">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="523e1-292">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="523e1-293">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="523e1-293">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="523e1-294">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="523e1-294">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="523e1-295">Появится сообщение «Соединение с сервером отчетов».</span><span class="sxs-lookup"><span data-stu-id="523e1-295">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="523e1-296">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов как место по умолчанию для отчетов.</span><span class="sxs-lookup"><span data-stu-id="523e1-296">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="523e1-297">В поле **Имя**замените имя по умолчанию фразой **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="523e1-297">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="523e1-298">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="523e1-298">Click **Save**.</span></span>  
  
 <span data-ttu-id="523e1-299">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="523e1-299">The report is saved to the report server.</span></span> <span data-ttu-id="523e1-300">Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="523e1-300">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="523e1-301">Сохранение отчета на компьютере</span><span class="sxs-lookup"><span data-stu-id="523e1-301">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="523e1-302">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="523e1-302">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="523e1-303">Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="523e1-303">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="523e1-304">В поле **Имя**замените имя по умолчанию фразой **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="523e1-304">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="523e1-305">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="523e1-305">Click **Save**.</span></span>  
  
##  <a name="7-export-the-report"></a><a name="Export"></a><span data-ttu-id="523e1-306">7. Экспорт отчета</span><span class="sxs-lookup"><span data-stu-id="523e1-306">7. Export the Report</span></span>  
 <span data-ttu-id="523e1-307">Отчеты можно экспортировать в различные форматы, например Microsoft Excel или CSV.</span><span class="sxs-lookup"><span data-stu-id="523e1-307">Reports can be exported to different formats such Microsoft Excel and comma separated value (CSV).</span></span> <span data-ttu-id="523e1-308">Дополнительные сведения см. в разделе [Экспорт отчетов &#40;построитель отчетов и службы SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="523e1-308">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="523e1-309">В этом учебнике описан экспорт отчета в формат Excel и задание свойства отчета, позволяющего присваивать пользовательские имена вкладкам книги.</span><span class="sxs-lookup"><span data-stu-id="523e1-309">In this tutorial, you will export the report to Excel and set a property on the report to provide a custom name for the workbook tab.</span></span>  
  
#### <a name="to-specify-the-workbook-tab-name"></a><span data-ttu-id="523e1-310">Присвоение имени вкладке книги</span><span class="sxs-lookup"><span data-stu-id="523e1-310">To specify the workbook tab name</span></span>  
  
1.  <span data-ttu-id="523e1-311">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="523e1-311">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="523e1-312">Щелкните в любом месте за пределами отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-312">Click anywhere outside the report.</span></span>  
  
3.  <span data-ttu-id="523e1-313">. На панели «Свойства» выберите свойство InitialPageName и введите « **продажи продукта Excel**».</span><span class="sxs-lookup"><span data-stu-id="523e1-313">.In the Properties pane, locate the InitialPageName property and type **Product Sales Excel**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="523e1-314">Если панель свойств не отображается, перейдите на вкладку Вид на ленте и нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="523e1-314">If the Properties pane is not visible, click the View tab on the ribbon, and then click **Properties**.</span></span>  
  
#### <a name="to-export-a-report-to-excel"></a><span data-ttu-id="523e1-315">Экспорт отчета в Excel</span><span class="sxs-lookup"><span data-stu-id="523e1-315">To export a report to Excel</span></span>  
  
1.  <span data-ttu-id="523e1-316">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="523e1-316">Click **Run** to preview the report.</span></span>  
  
2.  <span data-ttu-id="523e1-317">. На ленте нажмите кнопку **Экспорт**, а затем выберите пункт **Excel**.</span><span class="sxs-lookup"><span data-stu-id="523e1-317">.On the ribbon, click **Export**, and then click **Excel**.</span></span>  
  
     <span data-ttu-id="523e1-318">Откроется диалоговое окно **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="523e1-318">The **Save As** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="523e1-319">Перейдите в папку **документы** .</span><span class="sxs-lookup"><span data-stu-id="523e1-319">Browse to the **Documents** folder.</span></span>  
  
4.  <span data-ttu-id="523e1-320">В текстовом поле **имя файла** введите **продукт Sales Excel**.</span><span class="sxs-lookup"><span data-stu-id="523e1-320">In the **File name** text box, type **Product Sales Excel**.</span></span>  
  
5.  <span data-ttu-id="523e1-321">Убедитесь, что файл имеет тип **Книга Excel**.</span><span class="sxs-lookup"><span data-stu-id="523e1-321">Verify that the file type is **Excel Workbook**.</span></span>  
  
6.  <span data-ttu-id="523e1-322">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="523e1-322">Click **Save**.</span></span>  
  
#### <a name="to-view-the-report-in-excel"></a><span data-ttu-id="523e1-323">Просмотр отчета в Excel</span><span class="sxs-lookup"><span data-stu-id="523e1-323">To view the report in Excel</span></span>  
  
1.  <span data-ttu-id="523e1-324">Откройте папку **документы** и дважды щелкните **продукт продажи продуктов Excel.xlsx**.</span><span class="sxs-lookup"><span data-stu-id="523e1-324">Open the **Documents** folder and double click **Product Sales Excel.xlsx**.</span></span>  
  
2.  <span data-ttu-id="523e1-325">Убедитесь в том, что вкладка книги имеет имя **Продажи товаров Excel**.</span><span class="sxs-lookup"><span data-stu-id="523e1-325">Verify that the name of the workbook tab is **Product Sales Excel**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="523e1-326">Next Steps</span><span class="sxs-lookup"><span data-stu-id="523e1-326">Next Steps</span></span>  
 <span data-ttu-id="523e1-327">На этом пошаговое руководство по созданию простого табличного отчета закончено.</span><span class="sxs-lookup"><span data-stu-id="523e1-327">This concludes the walkthrough for how to create a basic table report.</span></span> <span data-ttu-id="523e1-328">Дополнительные сведения о таблицах см. в разделе [Таблицы, матрицы, списки &#40;построитель отчетов и службы SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="523e1-328">For more information about tables, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="523e1-329">См. также:</span><span class="sxs-lookup"><span data-stu-id="523e1-329">See Also</span></span>  
 <span data-ttu-id="523e1-330">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="523e1-330">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="523e1-331">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="523e1-331">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
