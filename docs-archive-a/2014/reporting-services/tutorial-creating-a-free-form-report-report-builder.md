---
title: Учебник. Создание отчета в свободной форме (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 87288b59-faf2-4b1d-a8e4-a7582baedf2f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 515b0d2566efa4e11216a28648338c7ec43f3950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737838"
---
# <a name="tutorial-creating-a-free-form-report-report-builder"></a><span data-ttu-id="b2e2e-102">Учебник. Создание отчета в свободной форме (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="b2e2e-102">Tutorial: Creating a Free Form Report (Report Builder)</span></span>
  <span data-ttu-id="b2e2e-103">В этом учебнике объясняется, как создать отчет SQL Server Reporting Services произвольной формы в виде стандартного письма.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-103">This tutorial teaches you how to create an SSRS free form report that resembles a forms letter.</span></span> <span data-ttu-id="b2e2e-104">Вы можете упорядочить элементы отчета, чтобы создать форму с текстовыми полями, изображениями и другими областями данных.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-104">You can arrange report items to create a form with text boxes, images and other data regions.</span></span>

 <span data-ttu-id="b2e2e-105">Отчет, который вы создаете в этом учебнике, строится на основе образца данных по продажам, включенного в учебник.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-105">The report you create in this tutorial is based on sample sales data that is included in the tutorial.</span></span> <span data-ttu-id="b2e2e-106">Отчет группирует сведения по территории и отображает имя менеджера по продажам на данной территории, а также подробные и сводные сведения о продажах.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-106">The report groups information by territory and displays the name of the sales manager for the territory as well as detailed and summary sales information.</span></span> <span data-ttu-id="b2e2e-107">Область списка данных используется как основа отчета в свободной форме, затем добавляются декоративная панель с изображением, статический текст со вставленными данными, таблица для отображения подробной информации и при необходимости круговые диаграммы и гистограммы со сводными данными.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-107">You will use the list data region as the foundation for the free form report, and then add a decorative panel with an image, static text with data inserted, a table to show detailed information, and optionally, pie and column charts to display summary information.</span></span>

##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="b2e2e-108">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="b2e2e-108">What You Will Learn</span></span>
 <span data-ttu-id="b2e2e-109">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="b2e2e-109">In this tutorial, you will learn how to do the following:</span></span>

-   [<span data-ttu-id="b2e2e-110">Создание пустого отчета, источника данных и набора данных</span><span class="sxs-lookup"><span data-stu-id="b2e2e-110">Create a Blank Report, Data Source, and Dataset</span></span>](#BlankReport)

-   [<span data-ttu-id="b2e2e-111">Добавление и настройка списка</span><span class="sxs-lookup"><span data-stu-id="b2e2e-111">Add and Configure a List</span></span>](#List)

-   [<span data-ttu-id="b2e2e-112">Добавление графических элементов</span><span class="sxs-lookup"><span data-stu-id="b2e2e-112">Add Graphics</span></span>](#Graphics)

-   [<span data-ttu-id="b2e2e-113">Добавление произвольного текста</span><span class="sxs-lookup"><span data-stu-id="b2e2e-113">Add Free Form Text</span></span>](#Text)

-   [<span data-ttu-id="b2e2e-114">Добавление таблицы для показа подробностей</span><span class="sxs-lookup"><span data-stu-id="b2e2e-114">Add a Table to Show Details</span></span>](#Table)

-   [<span data-ttu-id="b2e2e-115">Форматирование данных</span><span class="sxs-lookup"><span data-stu-id="b2e2e-115">Format Data</span></span>](#Format)

-   [<span data-ttu-id="b2e2e-116">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="b2e2e-116">Save the Report</span></span>](#Save)

### <a name="other-optional-steps"></a><span data-ttu-id="b2e2e-117">Другие дополнительные шаги</span><span class="sxs-lookup"><span data-stu-id="b2e2e-117">Other Optional Steps</span></span>

-   [<span data-ttu-id="b2e2e-118">Добавление строки в отдельные области отчета</span><span class="sxs-lookup"><span data-stu-id="b2e2e-118">Add a Line to Separate Areas of Report</span></span>](#Line)

-   [<span data-ttu-id="b2e2e-119">Добавление отображения сводных данных</span><span class="sxs-lookup"><span data-stu-id="b2e2e-119">Add Summary Data Visualization</span></span>](#Visualization)

 <span data-ttu-id="b2e2e-120">Предполагаемое время для выполнения заданий данного учебника: 20 минут</span><span class="sxs-lookup"><span data-stu-id="b2e2e-120">Estimated time to complete this tutorial: 20 minutes.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2e2e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b2e2e-121">Requirements</span></span>
 <span data-ttu-id="b2e2e-122">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="b2e2e-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>

##  <a name="1-create-a-blank-report-data-source-and-dataset"></a><a name="BlankReport"></a><span data-ttu-id="b2e2e-123">1. Создание пустого отчета, источника данных и набора данных</span><span class="sxs-lookup"><span data-stu-id="b2e2e-123">1. Create a Blank Report, Data Source, and Dataset</span></span>

> [!NOTE]
>  <span data-ttu-id="b2e2e-124">В этом учебнике запрос содержит значения данных, поэтому отчету не требуется внешний источник данных.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-124">In this tutorial, the query contains the data values so that the report does not need an external data source.</span></span> <span data-ttu-id="b2e2e-125">Использование этого типа внутренних данных отлично подходит в целях обучения, но делает запрос длинным.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-125">The use of this type of internal data is great for learning purposes, but the approach makes the query long.</span></span> <span data-ttu-id="b2e2e-126">.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-126">.</span></span>

#### <a name="to-create-a-blank-report"></a><span data-ttu-id="b2e2e-127">Создание пустого отчета</span><span class="sxs-lookup"><span data-stu-id="b2e2e-127">To create a blank report</span></span>

1.  <span data-ttu-id="b2e2e-128">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-128">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-129">Должно открыться диалоговое окно **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-129">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="b2e2e-130">Если этого не произойдет, из меню для кнопки «Построитель отчетов» выберите команду **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-130">If it does not, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="b2e2e-131">На левой панели диалогового окна **Приступая к работе** проверьте, выбран ли пункт **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-131">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>

3.  <span data-ttu-id="b2e2e-132">На правой панели щелкните **Пустой отчет**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-132">In the right pane, click **Blank Report**.</span></span>

#### <a name="to-create-a-new-data-source"></a><span data-ttu-id="b2e2e-133">Создание нового источника данных</span><span class="sxs-lookup"><span data-stu-id="b2e2e-133">To create a new data source</span></span>

1.  <span data-ttu-id="b2e2e-134">В области данных отчета нажмите кнопку **создать**, а затем выберите **источник данных**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-134">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>

2.  <span data-ttu-id="b2e2e-135">В `Name` поле введите: **ListDataSource** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-135">In the `Name` box, type: **ListDataSource**</span></span>

3.  <span data-ttu-id="b2e2e-136">Нажмите кнопку **Использовать соединение, внедренное в отчет**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-136">Click **Use a connection embedded in my report**.</span></span>

4.  <span data-ttu-id="b2e2e-137">Убедитесь, что тип соединения — Microsoft SQL Server, а затем в поле **строка подключения** введите: \*\*Data Source = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="b2e2e-137">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>

     <span data-ttu-id="b2e2e-138">\<servername>Например, Report001 указывает компьютер, на котором установлен экземпляр SQL Server ядро СУБД.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-138">\<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="b2e2e-139">Поскольку данные отчета не извлекаются из базы данных SQL Server, не нужно указывать имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-139">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="b2e2e-140">Для синтаксического анализа запроса используется база данных по умолчанию на указанном сервере.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-140">The default database on the specified server is used to parse the query.</span></span>

5.  <span data-ttu-id="b2e2e-141">Нажмите **Учетные данные**и введите учетные данные, необходимые для подключения к экземпляру ядра СУБД SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-141">Click **Credentials**, and enter the credentials needed to connect to the instance of the SQL Server Database Engine.</span></span>

6.  <span data-ttu-id="b2e2e-142">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-142">Click **OK**.</span></span>

#### <a name="to-create-a-new-dataset"></a><span data-ttu-id="b2e2e-143">Создание нового набора данных</span><span class="sxs-lookup"><span data-stu-id="b2e2e-143">To create a new dataset</span></span>

1.  <span data-ttu-id="b2e2e-144">В области данных отчета нажмите кнопку **создать**, а затем выберите **набор данных**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-144">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>

2.  <span data-ttu-id="b2e2e-145">В `Name` поле введите: **ListDataset.**</span><span class="sxs-lookup"><span data-stu-id="b2e2e-145">In the `Name` box, type: **ListDataset.**</span></span>

3.  <span data-ttu-id="b2e2e-146">Нажмите **Использовать включенный в мой отчет набор данных**, проверьте, что в качестве источника данных указан **ListDataSource**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-146">Click **Use a dataset embedded in my report**, and verify that the data source is **ListDataSource**.</span></span>

4.  <span data-ttu-id="b2e2e-147">Убедитесь, что выбран тип запроса **Текст** , и нажмите кнопку **Конструктор запросов**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-147">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>

5.  <span data-ttu-id="b2e2e-148">Нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-148">Click **Edit as Text**.</span></span>

6.  <span data-ttu-id="b2e2e-149">Скопируйте и вставьте на панели запросов следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="b2e2e-149">Copy and paste the following query into the query pane:</span></span>

    ```
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity
    ```

7.  <span data-ttu-id="b2e2e-150">Нажмите значок "Запуск", чтобы запустить запрос.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-150">Click Run icon to run the query.</span></span>

     <span data-ttu-id="b2e2e-151">Результаты запроса — это данные, доступные для отображения в отчете.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-151">The query results are the data available to display in your report.</span></span>

     <span data-ttu-id="b2e2e-152">![Конструктор запросов](../../2014/tutorials/media/tutorial-querydesigner.png "Конструктор запросов")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-152">![Query Designer](../../2014/tutorials/media/tutorial-querydesigner.png "Query Designer")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="2-add-and-configure-a-list"></a><a name="List"></a><span data-ttu-id="b2e2e-153">2. Добавление и Настройка списка</span><span class="sxs-lookup"><span data-stu-id="b2e2e-153">2. Add and Configure a List</span></span>
 <span data-ttu-id="b2e2e-154">Службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] предоставляют три шаблона области данных: таблицу, матрицу и список.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-154">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides three data region templates: table, matrix, and list.</span></span> <span data-ttu-id="b2e2e-155">Все эти шаблоны основаны на области данных табликса.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-155">These templates are all based on a tablix data region.</span></span>

 <span data-ttu-id="b2e2e-156">В данном учебнике вы будете использовать список для отображения сведений о территориальных продажах в отчете, напоминающем информационный бюллетень.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-156">In this tutorial, you will use a list to display the sales information for sales territories in a report that resembles a newsletter.</span></span> <span data-ttu-id="b2e2e-157">Сведения группируются по территориям.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-157">The information is grouped by territory.</span></span> <span data-ttu-id="b2e2e-158">Добавьте новую группу строк, в которой данные группируются по территориям, а затем удалите встроенную группу строк подробностей.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-158">You will add a new row group that groups data by territory, and then delete the built-in Details row group.</span></span> <span data-ttu-id="b2e2e-159">Шаблон списка идеально подходит для создания отчетов произвольной формы.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-159">The list template is ideal for creating free form reports.</span></span> <span data-ttu-id="b2e2e-160">Дополнительные сведения см. в разделе [lists &#40;построитель отчетов and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b2e2e-160">For more information, see [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="b2e2e-161">Для отчета используются размер бумаги Letter (8,5 X11) и поля шириной 1 дюйм.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-161">This report uses the paper size Letter (8.5 X11) and 1 inch margins.</span></span> <span data-ttu-id="b2e2e-162">Страница отчета высотой более 9 дюймов или шириной более 6,5 дюймов может привести к формированию пустых страниц.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-162">A report page taller than 9 inches or wider than 6 1/2 inches might generate blank pages.</span></span>

#### <a name="to-add-a-list"></a><span data-ttu-id="b2e2e-163">Добавление списка</span><span class="sxs-lookup"><span data-stu-id="b2e2e-163">To add a list</span></span>

1.  <span data-ttu-id="b2e2e-164">На вкладке ленты **Вставка** в разделе **Области данных** щелкните **Список** , а затем перетащите список в текст отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-164">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List** and then drag the list inside the report body.</span></span> <span data-ttu-id="b2e2e-165">Установите для списка высоту в 7 дюймов и ширину в 6,25 дюйма.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-165">Make the list 7 inches tall and 6.25 inches wide.</span></span>

2.  <span data-ttu-id="b2e2e-166">Щелкните внутри списка, щелкните правой кнопкой мыши на вершине списка и выберите **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-166">Click inside the list, right-click the top of the list, and then click **Tablix Properties**.</span></span>

     <span data-ttu-id="b2e2e-167">![Список добавления](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Список добавления")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-167">![Adding list](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Adding list")</span></span>

3.  <span data-ttu-id="b2e2e-168">В раскрывающемся списке **Имя набора данных** выберите пункт **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-168">In the **Dataset name** drop-down list, select **ListDataset**.</span></span>

4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

5.  <span data-ttu-id="b2e2e-169">Щелкните правой кнопкой мыши внутри списка и выберите пункт **Свойства прямоугольной области**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-169">Right-click inside the list, and then click **Rectangle Properties**.</span></span>

     <span data-ttu-id="b2e2e-170">![Команда "Свойства прямоугольника"](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Команда "Свойства прямоугольника"")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-170">![Rectangle Properties command](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Rectangle Properties command")</span></span>

6.  <span data-ttu-id="b2e2e-171">На вкладке **Общие** установите флажок **Вставить разрыв страницы после** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-171">On the **General** tab, select the **Add a page break after** checkbox.</span></span>

7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-new-row-group-and-to-delete-the-details-group"></a><span data-ttu-id="b2e2e-172">Добавление новой группы строк и удаление группы подробностей</span><span class="sxs-lookup"><span data-stu-id="b2e2e-172">To add a new row group and to delete the Details group</span></span>

1.  <span data-ttu-id="b2e2e-173">На панели "Группы строк" щелкните правой кнопкой мыши группу подробностей, выберите пункт **Добавить группу**, а затем пункт **Родительская группа**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-173">In the Row Groups pane, right-click the Details group, point to **Add Group**, and then click **Parent Group**.</span></span>

     <span data-ttu-id="b2e2e-174">![Команда "Родительская группа"](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Команда "Родительская группа"")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-174">![Parent Group command](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Parent Group command")</span></span>

2.  <span data-ttu-id="b2e2e-175">В раскрывающемся списке выберите `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="b2e2e-175">In the drop-down list, select `[Territory].`</span></span>

3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="b2e2e-176">В список добавится столбец.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-176">A column is added to the list.</span></span> <span data-ttu-id="b2e2e-177">Столбец содержит ячейку `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="b2e2e-177">The column contains the cell `[Territory].`</span></span>

4.  <span data-ttu-id="b2e2e-178">Щелкните правой кнопкой мыши столбец "Территория" в списке и выберите команду **Удалить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-178">Right-click the Territory column in the list, and then click **Delete Columns**.</span></span>

     <span data-ttu-id="b2e2e-179">![Удалить столбцы](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Удалить столбцы")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-179">![Delete columns](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Delete columns")</span></span>

5.  <span data-ttu-id="b2e2e-180">Выберите **Удалить только столбцы**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-180">Click **Delete Columns only**.</span></span>

     <span data-ttu-id="b2e2e-181">![Диалоговое окно «Удаление столбцов»](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "диалоговое окно «Удаление столбцов»")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-181">![Delete Columns dialog box](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Delete Columns dialog box")</span></span>

6.  <span data-ttu-id="b2e2e-182">На панели "Группы строк" щелкните правой кнопкой мыши группу **Подробности** , выберите пункт **Удалить группу**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-182">In the Row Groups pane, right-click the **Details** group, and then click **Delete Group**.</span></span>

     <span data-ttu-id="b2e2e-183">![Удаление группы сведений](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Удаление группы сведений")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-183">![Delete Details Group](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Delete Details Group")</span></span>

7.  <span data-ttu-id="b2e2e-184">Щелкните **Удалить только группу**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-184">Click **Delete Group only**.</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="3-add-graphics"></a><a name="Graphics"></a><span data-ttu-id="b2e2e-185">3. Добавление графики</span><span class="sxs-lookup"><span data-stu-id="b2e2e-185">3. Add Graphics</span></span>
 <span data-ttu-id="b2e2e-186">Одно из преимуществ использования области списка данных заключается в возможности добавлять в любом месте такие элементы отчета, как прямоугольники и текстовые поля, не ограничиваясь табличным макетом.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-186">One of the advantages of using a list data region is that you can add report items such as rectangles and text boxes anywhere, instead of being limited to a tabular layout.</span></span> <span data-ttu-id="b2e2e-187">Внешний вид отчета улучшается благодаря добавлению графических элементов (прямоугольника с цветной заливкой).</span><span class="sxs-lookup"><span data-stu-id="b2e2e-187">You will enhance the appearance of the report by adding a graphic (a rectangle filled with a color).</span></span>

#### <a name="to-add-graphic-elements-to-the-report"></a><span data-ttu-id="b2e2e-188">Добавление графических элементов в отчет</span><span class="sxs-lookup"><span data-stu-id="b2e2e-188">To add graphic elements to the report</span></span>

1.  <span data-ttu-id="b2e2e-189">На вкладке ленты **Вставка** щелкните **прямоугольник**, а затем перетащите прямоугольник в верхний левый угол списка.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-189">On the **Insert** tab of the ribbon, click **Rectangle**,and then drag a rectangle to the upper left corner of the list.</span></span> <span data-ttu-id="b2e2e-190">Установите высоту прямоугольника 7 дюймов и ширину 1 дюйм.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-190">Make the rectangle 7 inches tall and 1 inch wide.</span></span>

2.  <span data-ttu-id="b2e2e-191">Щелкните правой кнопкой мыши прямоугольник, затем выберите пункт **Свойства прямоугольника**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-191">Right-click the rectangle, and then click **Rectangle Properties**.</span></span>

3.  <span data-ttu-id="b2e2e-192">Перейдите на вкладку **Заливка** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-192">Click the **Fill** tab.</span></span>

4.  <span data-ttu-id="b2e2e-193">В раскрывающемся списке **Цвет заливки** нажмите **Другие цвета**и выберите **темно-серый** цвет.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-193">In the **Fill color** drop-down list, click **More Colors**, and then select the **DarkGray** color.</span></span>

     <span data-ttu-id="b2e2e-194">![Выбор цвета заливки](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Выбор цвета заливки")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-194">![Select fill color](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Select fill color")</span></span>

5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

6.  <span data-ttu-id="b2e2e-195">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-195">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b2e2e-196">В левой стороне отчета теперь находится вертикальный графический элемент, состоящий из синевато-серого прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-196">The left side of the report now has vertical graphic that consists of a dark gray rectangle.</span></span>

##  <a name="4-add-free-form-text"></a><a name="Text"></a><span data-ttu-id="b2e2e-197">4. Добавление текста свободной формы</span><span class="sxs-lookup"><span data-stu-id="b2e2e-197">4. Add Free Form Text</span></span>
 <span data-ttu-id="b2e2e-198">Текстовое поле содержит статический текст, повторяемый на каждой странице отчета, а также поля данных.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-198">A text box contains static text that is repeated on each report page as well as data fields.</span></span>

#### <a name="to-add-text-to-the-report"></a><span data-ttu-id="b2e2e-199">Добавление текста в отчет</span><span class="sxs-lookup"><span data-stu-id="b2e2e-199">To add text to the report</span></span>

1.  <span data-ttu-id="b2e2e-200">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-200">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="b2e2e-201">На вкладке **Вставка** ленты нажмите **Текстовое поле**и перетащите текстовое поле в верхний левый угол списка, но внутри добавленного ранее прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-201">On the **Insert** tab of the ribbon, click **Text Box**, and then drag a text box to the upper left corner of the list, but inside of the rectangle you added previously.</span></span> <span data-ttu-id="b2e2e-202">Приближенно установите высоту текстового поля 3 дюйма и ширину 5 дюймов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-202">Make the text box about 3 inches tall and 5 inches wide.</span></span>

3.  <span data-ttu-id="b2e2e-203">Поместите курсор в верхнюю часть текстового поля и введите **Newsletter for** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-203">Place the cursor in the upper part of the text box, and then type: **Newsletter for** .</span></span>

     <span data-ttu-id="b2e2e-204">![Добавление текста заголовка бюллетеня](../../2014/tutorials/media/tutorial-newsletterfor.png "Добавление текста заголовка бюллетеня")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-204">![Add newsletter heading text](../../2014/tutorials/media/tutorial-newsletterfor.png "Add newsletter heading text")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-205">Не забудьте вставить дополнительный пробел после слова «for».</span><span class="sxs-lookup"><span data-stu-id="b2e2e-205">Be sure to include the extra space after the word "for".</span></span> <span data-ttu-id="b2e2e-206">Пробел отделяет текст от поля, которое будет добавлено в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-206">The space separates the text and the field that you will add in the next step.</span></span>

4.  <span data-ttu-id="b2e2e-207">Перетащите поле Territory в текстовое поле и поместите его после текста, введенного в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-207">Drag the Territory field to the text box and place it after the text you typed in step 3.</span></span>

     <span data-ttu-id="b2e2e-208">![Добавление поля "Территория"](../../2014/tutorials/media/tutorial-addterritorialfield.png "Добавление поля "Территория"")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-208">![Add Territorial field](../../2014/tutorials/media/tutorial-addterritorialfield.png "Add Territorial field")</span></span>

5.  <span data-ttu-id="b2e2e-209">Выделите весь текст, щелкните его правой кнопкой мыши и выберите пункт **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-209">Select all text, right-click, and then click **Text Properties**.</span></span>

6.  <span data-ttu-id="b2e2e-210">Перейдите на вкладку **Шрифт** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-210">Click the **Font** tab.</span></span>

7.  <span data-ttu-id="b2e2e-211">В списке **Шрифт** выберите **Times New Roman**; в списке **Размер** выберите **20 пт**, в списке **Цвет** выберите **Красный**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-211">In the **Font** list, select **Times New Roman**; in **Size** select **20 pt**, in **Color** select **Red**.</span></span>

     <span data-ttu-id="b2e2e-212">![Свойства текста](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Свойства текста")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-212">![Text Properties](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Text Properties")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

9. <span data-ttu-id="b2e2e-213">Поместите курсор ниже текста, введенного в шаге 3, и введите **Hello** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-213">Place the cursor below the text you typed in step 3 and type: **Hello** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-214">Не забудьте вставить дополнительный пробел после слова «Hello».</span><span class="sxs-lookup"><span data-stu-id="b2e2e-214">Be sure to include the extra space after the word "Hello".</span></span> <span data-ttu-id="b2e2e-215">Пробел отделяет текст от поля, которое будет добавлено в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-215">The space separates the text and the field that you will add in the next step.</span></span>

10. <span data-ttu-id="b2e2e-216">Перетащите поле FullName в текстовое поле и поместите его после текста, введенного в шаге 9, а затем поставьте запятую (,).</span><span class="sxs-lookup"><span data-stu-id="b2e2e-216">Drag the FullName field to the text box and place it after the text you typed in step 9, and then type a comma (,).</span></span>

     <span data-ttu-id="b2e2e-217">![Добавление поля "Полное имя"](../../2014/tutorials/media/tutorial-addfullnamefield.png "Добавление поля "Полное имя"")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-217">![Add Full Name field](../../2014/tutorials/media/tutorial-addfullnamefield.png "Add Full Name field")</span></span>

11. <span data-ttu-id="b2e2e-218">Выделите текст, добавленный в шагах 9 и 10, щелкните правой кнопкой мыши, а затем выберите **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-218">Select the text you added in steps 9 and 10, right-click, and then click **Text Properties**.</span></span>

12. <span data-ttu-id="b2e2e-219">Перейдите на вкладку **Шрифт** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-219">Click the **Font** tab.</span></span>

13. <span data-ttu-id="b2e2e-220">В списке **Шрифт** выберите **Times New Roman**; в списке **Размер** выберите **16 пт**, в списке **Цвет** выберите **Черный** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-220">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Black** color.</span></span>

14. [!INCLUDE[clickOK](../includes/clickok-md.md)]

15. <span data-ttu-id="b2e2e-221">Разместите курсор ниже текста, добавленного в шагах с 9 по 13, а затем скопируйте и вставьте следующий текст-заполнитель:</span><span class="sxs-lookup"><span data-stu-id="b2e2e-221">Place the cursor below the text you added in steps 9 through 13, and then copy and paste the following "greeked" text:</span></span>

    ```
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sed dolor in ipsum pulvinar egestas. Sed sed lacus at leo ornare ultricies. Vivamus velit risus, euismod nec sodales gravida, gravida in dui. Etiam ullamcorper elit vitae justo fermentum ut ullamcorper augue sodales. Ut placerat, nisl quis feugiat adipiscing, nibh est aliquet est, mollis faucibus mauris lectus quis arcu. In mollis tincidunt lacinia. In vitae erat ut lorem tincidunt luctus. Curabitur et magna nunc, sit amet adipiscing nisi. Nulla rhoncus elementum orci nec tincidunt. Aliquam imperdiet cursus erat vel tincidunt. Donec et neque ac urna rutrum sodales. In id purus et nisl dignissim dapibus. Sed rhoncus metus at felis feugiat eu tempor dolor vehicula. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam faucibus consectetur diam eu pellentesque. 
    Nulla facilisi. Proin ligula enim, porta ut tincidunt id, adipiscing sit amet eros. Ut purus sem, bibendum et vulputate sit amet, facilisis eget magna. Sed aliquam erat non erat eleifend hendrerit. Ut a ligula est, sit amet eleifend enim. Ut et nisl enim, sit amet adipiscing augue. Vivamus eu arcu ac libero posuere elementum. Integer condimentum bibendum venenatis. Integer odio tellus, feugiat in pellentesque semper, interdum nec sem. Sed cursus euismod sem, ut elementum sapien placerat vel. 
    ```

16. <span data-ttu-id="b2e2e-222">Выделите текст, добавленный в шаге 15, щелкните правой кнопкой мыши, а затем выберите **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-222">Select the text you added in steps 15, right-click, and then click **Text Properties**.</span></span>

17. <span data-ttu-id="b2e2e-223">Перейдите на вкладку **Шрифт** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-223">Click the **Font** tab.</span></span>

18. <span data-ttu-id="b2e2e-224">В списке **Шрифт** выберите **Arial**, в списке **Размер** выберите **10 пт**, в списке **Цвет** выберите **Черный**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-224">In the **Font** list, select **Arial**; in **Size** select **10 pt**, in **Color** select **Black**.</span></span>

19. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="b2e2e-225">![Добавление текста бюллетеня](../../2014/tutorials/media/tutorial-newslettertext.png "Добавление текста бюллетеня")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-225">![Add newsletter text](../../2014/tutorials/media/tutorial-newslettertext.png "Add newsletter text")</span></span>

20. <span data-ttu-id="b2e2e-226">Поместите курсор ниже текста, вставленного в шаге 15, а затем введите **Congratulations on your total sales of** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-226">Place the cursor below the text you pasted in step 15, and then type: **Congratulations on your total sales of** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-227">Не забудьте вставить дополнительный пробел после слова «of».</span><span class="sxs-lookup"><span data-stu-id="b2e2e-227">Be sure to include the extra space after the word "of".</span></span> <span data-ttu-id="b2e2e-228">Пробел отделяет текст от поля, которое будет добавлено в следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-228">The space separates the text and the field that you will add in the next step.</span></span>

21. <span data-ttu-id="b2e2e-229">Перетащите поле Sales в текстовое поле, поместите его после текста, введенного в шаге 20, а затем поставьте восклицательный знак (!).</span><span class="sxs-lookup"><span data-stu-id="b2e2e-229">Drag the Sales field to the text box, place it after the text you typed in step 20, and then type an exclamation mark (!).</span></span>

22. <span data-ttu-id="b2e2e-230">Выделите поле Sales (продажи), щелкните правой кнопкой мыши поле и выберите пункт **выражение**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-230">Highlight the Sales field, right-click the field, and then click **Expression**.</span></span>

23. <span data-ttu-id="b2e2e-231">В поле выражений измените выражение, включив функцию Sum следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b2e2e-231">In the expression box, change the expression to include the Sum function as follows:</span></span>

    ```
    =Sum(Fields!Sales.value)
    ```

24. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="b2e2e-232">![Добавление выражения в поле продаж](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Добавление выражения в поле продаж")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-232">![Add an expression to sales field](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Add an expression to sales field")</span></span>

25. <span data-ttu-id="b2e2e-233">Выделите текст, добавленный в шагах с 20 по 23, щелкните правой кнопкой мыши, а затем выберите **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-233">Select the text you added in steps 20 through 23, right-click, and then click **Text Properties**.</span></span>

26. <span data-ttu-id="b2e2e-234">Перейдите на вкладку **Шрифт** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-234">Click the **Font** tab.</span></span>

27. <span data-ttu-id="b2e2e-235">В списке **Шрифт** выберите **Times New Roman**, в списке **Размер** выберите **16 пт**, в списке **Цвет** выберите **Красный**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-235">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Red**.</span></span>

28. [!INCLUDE[clickOK](../includes/clickok-md.md)]

29. <span data-ttu-id="b2e2e-236">Выберите `[Sum(Sales)]` и на вкладке **Главная** , в группе **Число** нажмите кнопку **Валюта** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-236">Select `[Sum(Sales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="b2e2e-237">![Добавление символа валюты](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Добавление символа валюты")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-237">![Add currency symbol](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Add currency symbol")</span></span>

30. <span data-ttu-id="b2e2e-238">Щелкните правой кнопкой текстовое поле с текстом "Щелкните, чтобы добавить заголовок", а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-238">Right-click the text box with the "Click to add title" text, and then click **Delete**.</span></span>

31. <span data-ttu-id="b2e2e-239">Выберите поле списка и с помощью клавиш со стрелками переместите его в верхнюю часть страницы.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-239">Select the list box and using the arrow keys, move it to the top of the page.</span></span>

32. <span data-ttu-id="b2e2e-240">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-240">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b2e2e-241">В отчете отображается статический текст, и каждая страница отчета содержит данные для определенной территории.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-241">The report displays static text and each report page includes data that pertains to a territory.</span></span> <span data-ttu-id="b2e2e-242">Данные о продажах форматируются как денежные значения.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-242">Sales are formatted as currency.</span></span>

 <span data-ttu-id="b2e2e-243">![Предварительный просмотр бюллетеня](../../2014/tutorials/media/tutorial-newsletters.png "Предварительный просмотр бюллетеня")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-243">![Preview of Newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Preview of Newsletter")</span></span>

##  <a name="5-add-a-table-to-show-sales-details"></a><a name="Table"></a><span data-ttu-id="b2e2e-244">5. Добавление таблицы для отображения сведений о продажах</span><span class="sxs-lookup"><span data-stu-id="b2e2e-244">5. Add a Table to Show Sales Details</span></span>
 <span data-ttu-id="b2e2e-245">Используйте мастер создания новой таблицы или матрицы, чтобы добавить таблицу в отчет произвольной формы.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-245">Use the New Table and Matrix Wizard to add a table to the free form report.</span></span> <span data-ttu-id="b2e2e-246">После завершения работы мастера добавьте вручную строку для итогов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-246">After you complete the wizard, you will manually add a row for totals.</span></span>

#### <a name="to-add-a-table"></a><span data-ttu-id="b2e2e-247">Добавление таблицы</span><span class="sxs-lookup"><span data-stu-id="b2e2e-247">To add a table</span></span>

1.  <span data-ttu-id="b2e2e-248">На вкладке ленты **Вставка** в разделе **Области данных** выберите **Таблица**, а затем щелкните **Мастер таблиц**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-248">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **Table**, and then click **Table Wizard**.</span></span>

2.  <span data-ttu-id="b2e2e-249">На странице «Выбор набора данных» выберите **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-249">On the Choose a dataset page, click **ListDataset**.</span></span>

3.  <span data-ttu-id="b2e2e-250">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-250">Click **Next**.</span></span>

4.  <span data-ttu-id="b2e2e-251">На странице **Выравнивание полей** перетащите поле Product из раздела **Доступные поля** в **Значения**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-251">On the **Arrange fields** page, drag the Product field from **Available fields** to **Values.**</span></span>

5.  <span data-ttu-id="b2e2e-252">Повторите шаг 4 для SalesDate, Quantity и Sales.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-252">Repeat step 4, for SalesDate, Quantity, and Sales.</span></span> <span data-ttu-id="b2e2e-253">Поместите SalesDate ниже Product, Quantity ниже SalesDate, а Sales ниже SalesDate.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-253">Place SalesDate below Product, Quantity below SalesDate, and Sales below SalesDate.</span></span>

6.  <span data-ttu-id="b2e2e-254">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-254">Click **Next**.</span></span>

7.  <span data-ttu-id="b2e2e-255">На странице **Выбор макета** можно просмотреть макет таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-255">On the **Choose the layout** page, view the layout of the table.</span></span>

     <span data-ttu-id="b2e2e-256">Таблица очень проста.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-256">The table is very simple.</span></span> <span data-ttu-id="b2e2e-257">Она состоит из пяти столбцов и не имеет групп строк или столбцов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-257">It consists of five columns and has no row or column groups.</span></span> <span data-ttu-id="b2e2e-258">Поскольку группы отсутствуют, недоступны варианты макета, связанные с группами.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-258">Because it has no groups, the layout options related to groups, are not available.</span></span> <span data-ttu-id="b2e2e-259">Далее в учебнике таблица будет обновлена вручную для добавления итога.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-259">You will manually update the table to include a total later in the tutorial.</span></span>

8.  <span data-ttu-id="b2e2e-260">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-260">Click **Next**.</span></span>

9. <span data-ttu-id="b2e2e-261">На странице **Выбор стиля** панели **Стили** выберите **Сланец**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-261">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

10. <span data-ttu-id="b2e2e-262">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-262">Click **Finish**.</span></span>

11. <span data-ttu-id="b2e2e-263">Перетащите таблицу ниже текстового поля, добавленного в занятии 4.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-263">Drag the table to below the text box that you added in lesson 4.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-264">Убедитесь, что таблица находится внутри списка.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-264">Make sure the table is inside the list.</span></span>

12. <span data-ttu-id="b2e2e-265">Убедившись, что таблица выбрана, щелкните правой кнопкой мыши затем панель группы строк "Сведения", выберите пункт **Добавить итоговое значение**, нажмите **После**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-265">Confirmed that the table is selected, then in the Row Group pane right-click Details, point to **Add Total**, and then click **After**.</span></span>

     <span data-ttu-id="b2e2e-266">![Добавление общего отчета](../../2014/tutorials/media/tutorial-addtotal.png "Добавление общего отчета")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-266">![Add report total](../../2014/tutorials/media/tutorial-addtotal.png "Add report total")</span></span>

13. <span data-ttu-id="b2e2e-267">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-267">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b2e2e-268">Отчет отображает таблицу со сведениями о продажах и итогами.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-268">The report displays a table with sales details and totals.</span></span>

 <span data-ttu-id="b2e2e-269">![Объем продаж в отчете](../../2014/tutorials/media/tutorial-reportsalestotals.png "Объем продаж в отчете")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-269">![Sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals.png "Sales totals in report")</span></span>

##  <a name="6-format-data"></a><a name="Format"></a><span data-ttu-id="b2e2e-270">6. Форматирование данных</span><span class="sxs-lookup"><span data-stu-id="b2e2e-270">6. Format Data</span></span>
 <span data-ttu-id="b2e2e-271">Числовые данные форматируются как денежное значение, а даты — только как день и время.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-271">Format numeric data as currency and dates as day and time only.</span></span>

#### <a name="to-format-fields-table"></a><span data-ttu-id="b2e2e-272">Форматирование таблицы с полями</span><span class="sxs-lookup"><span data-stu-id="b2e2e-272">To format fields table</span></span>

1.  <span data-ttu-id="b2e2e-273">Нажмите кнопку **конструктор** , чтобы перейти в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-273">Click **Design** to switch to design view.</span></span>

2.  <span data-ttu-id="b2e2e-274">Выберите ячейки таблицы, которые содержат `[Sum(SalesSales)]` , и на вкладке **Главная** в группе **Число** нажмите кнопку **Валюта** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-274">Click the table cells that contain `[Sum(SalesSales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="b2e2e-275">![Добавление символа валюты в сумму продаж](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Добавление символа валюты в сумму продаж")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-275">![Add currency symbol to sum sales](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Add currency symbol to sum sales")</span></span>

3.  <span data-ttu-id="b2e2e-276">Щелкните ячейку, содержащую `[SalesDate]` , и в группе **Число** выберите **Дата**из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-276">Click the cell that contains `[SalesDate]` and in the **Number** group, from the drop-down list, select **Date**.</span></span>

4.  <span data-ttu-id="b2e2e-277">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-277">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b2e2e-278">Теперь отчет содержит форматированные данные и более удобен для чтения.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-278">The report now displays formatted data and is easier to read.</span></span>

 <span data-ttu-id="b2e2e-279">![Формат объема продаж в отчете](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Формат объема продаж в отчете")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-279">![Format sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Format sales totals in report")</span></span>

##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="b2e2e-280">7. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="b2e2e-280">7. Save the Report</span></span>
 <span data-ttu-id="b2e2e-281">Отчеты можно сохранять на сервере отчетов, в библиотеке SharePoint или на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-281">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="b2e2e-282">Вы также можете экспортировать отчет в разные форматы, например в Word или в PDF, запустив отчет и выбрав формат в меню **Экспорт** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-282">You can also export the report to a variety of formats such as Word and PDF, by running the report and selecting the format from the **Export** menu.</span></span>

 <span data-ttu-id="b2e2e-283">В данном учебнике предусмотрено сохранение отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-283">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="b2e2e-284">Если нет доступа к серверу отчетов, сохраните отчет на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-284">If you do not have access to a report server, save the report to your computer.</span></span>

#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="b2e2e-285">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="b2e2e-285">To save the report on a report server</span></span>

1.  <span data-ttu-id="b2e2e-286">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-286">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="b2e2e-287">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-287">Click **Recent Sites and Servers**.</span></span>

3.  <span data-ttu-id="b2e2e-288">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-288">Select or type the name of the report server where you have permission to save reports.</span></span>

     <span data-ttu-id="b2e2e-289">Появится сообщение «Соединение с сервером отчетов».</span><span class="sxs-lookup"><span data-stu-id="b2e2e-289">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="b2e2e-290">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов как место по умолчанию для отчетов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-290">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>

4.  <span data-ttu-id="b2e2e-291">В `Name` замените имя по умолчанию на **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-291">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

5.  <span data-ttu-id="b2e2e-292">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-292">Click **Save**.</span></span>

 <span data-ttu-id="b2e2e-293">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-293">The report is saved to the report server.</span></span> <span data-ttu-id="b2e2e-294">Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-294">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>

#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="b2e2e-295">Сохранение отчета на компьютере</span><span class="sxs-lookup"><span data-stu-id="b2e2e-295">To save the report on your computer</span></span>

1.  <span data-ttu-id="b2e2e-296">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-296">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="b2e2e-297">Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-297">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>

3.  <span data-ttu-id="b2e2e-298">В `Name` замените имя по умолчанию на **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-298">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

4.  <span data-ttu-id="b2e2e-299">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-299">Click **Save**.</span></span>

##  <a name="8-optional-add-a-line-to-separate-areas-of-the-report"></a><a name="Line"></a><span data-ttu-id="b2e2e-300">8. Добавление строки в отдельные области отчета (необязательно)</span><span class="sxs-lookup"><span data-stu-id="b2e2e-300">8. (Optional) Add a Line to Separate Areas of the Report</span></span>
 <span data-ttu-id="b2e2e-301">Добавление строки в отдельные области редактирования и подробностей отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-301">Add a line to separate the editorial and details areas of the report.</span></span>

#### <a name="to-add-a-line"></a><span data-ttu-id="b2e2e-302">Добавление линии</span><span class="sxs-lookup"><span data-stu-id="b2e2e-302">To add a line</span></span>

1.  <span data-ttu-id="b2e2e-303">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-303">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="b2e2e-304">На вкладке ленты **Вставка** в области **Элементы отчета** щелкните **Линия**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-304">On the **Insert** tab of the ribbon, in the **Report Items** area, click **Line.**</span></span>

3.  <span data-ttu-id="b2e2e-305">Проведите линию ниже поля произвольного текста, добавленного в занятии 4.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-305">Draw a line below the free form text box you added in lesson 4.</span></span>

4.  <span data-ttu-id="b2e2e-306">Щелкните линию.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-306">Click the line.</span></span>

5.  <span data-ttu-id="b2e2e-307">Перейдите на вкладку **Главная** .</span><span class="sxs-lookup"><span data-stu-id="b2e2e-307">Click the **Home** tab.</span></span>

6.  <span data-ttu-id="b2e2e-308">В области **Контур** выберите ширину **4,5** пт, цвет выберите **Красный**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-308">In the **Border** area, for width select **4 1/2** pt and for color, for color select **Red**.</span></span>

     <span data-ttu-id="b2e2e-309">![Добавление линии в отчет](../../2014/tutorials/media/tutorial-reportwithline.png "Добавление линии в отчет")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-309">![Add line to report](../../2014/tutorials/media/tutorial-reportwithline.png "Add line to report")</span></span>

##  <a name="9-optional-add-summary-data-visualization"></a><a name="Visualization"></a><span data-ttu-id="b2e2e-310">9. добавление визуализации сводных данных (необязательно)</span><span class="sxs-lookup"><span data-stu-id="b2e2e-310">9. (Optional) Add Summary Data Visualization</span></span>
 <span data-ttu-id="b2e2e-311">С помощью прямоугольников можно управлять подготовкой отчетов к просмотру.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-311">Rectangles help you control how the report renders.</span></span> <span data-ttu-id="b2e2e-312">Поместите круговую диаграмму и гистограмму в прямоугольник, чтобы отчет был правильно подготовлен к просмотру.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-312">Place a pie and column chart inside a rectangle to ensure that the report renders the way you want.</span></span>

#### <a name="to-add-a-rectangle"></a><span data-ttu-id="b2e2e-313">Добавление прямоугольника</span><span class="sxs-lookup"><span data-stu-id="b2e2e-313">To add a rectangle</span></span>

1.  <span data-ttu-id="b2e2e-314">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-314">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="b2e2e-315">На вкладке ленты **Вставка** в области **Элементы отчета** выберите **Прямоугольник**, а затем перетащите прямоугольник в список справа от таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-315">On the **Insert** tab of the ribbon, in the **Report Items** area click **Rectangle**, and then drag the rectangle inside the list, to the right of the table.</span></span> <span data-ttu-id="b2e2e-316">Установите ширину прямоугольника 2 дюйма и высоту 4 дюйма.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-316">Make the rectangle 2 inches wide and 4 inches tall.</span></span>

3.  <span data-ttu-id="b2e2e-317">Выровняйте верхний край прямоугольника с верхним краем таблицы.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-317">Align the tops of the rectangle and the table.</span></span>

#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="b2e2e-318">Добавление круговой диаграммы</span><span class="sxs-lookup"><span data-stu-id="b2e2e-318">To add a pie chart</span></span>

1.  <span data-ttu-id="b2e2e-319">На вкладке **Вставка** ленты в области **Визуализации данных** нажмите **Диаграмма** , затем — **Мастер диаграмм**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-319">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="b2e2e-320">На странице Выбор набора данных нажмите **ListDataset**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-320">On the Choose a dataset page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="b2e2e-321">Нажмите кнопку **Круговая диаграмма**, а затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-321">Click **Pie**, and then click **Next**.</span></span>

4.  <span data-ttu-id="b2e2e-322">На странице "Размещение полей диаграммы" перетащите поле Product в **Категории**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-322">On the arrange chart fields page, drag Product to **Categories**.</span></span>

5.  <span data-ttu-id="b2e2e-323">Перетащите поле Quantity в **значения**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-323">Drag Quantity to **Values**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b2e2e-324">На странице **Выбор стиля** панели **Стили** выберите **Сланец**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-324">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="b2e2e-325">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-325">Click **Finish**.</span></span>

8.  <span data-ttu-id="b2e2e-326">Измените размеры диаграммы, показанной в верхнем левом углу отчета, установив высоту 1 1/2 дюйма и ширину 2 дюйма.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-326">Resize the chart that appears in the upper left corner of the report, to be 1 1/2 inches tall and 2 inches wide.</span></span>

9. <span data-ttu-id="b2e2e-327">Перетащите диаграмму в прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-327">Drag the chart inside the rectangle.</span></span>

     <span data-ttu-id="b2e2e-328">![Добавление круговой диаграммы](../../2014/tutorials/media/tutorial-addpiechart.png "Добавление круговой диаграммы")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-328">![Add pie chart](../../2014/tutorials/media/tutorial-addpiechart.png "Add pie chart")</span></span>

10. <span data-ttu-id="b2e2e-329">Правой кнопкой мыши щелкните заголовок диаграммы, затем нажмите **Свойства заголовка диаграммы**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-329">Right-click the chart title, and then click **Title Properties**.</span></span>

11. <span data-ttu-id="b2e2e-330">В диалоговом окне **Свойства заголовка диаграммы** в поле «Текст заголовка» введите **Product Quantities Sold**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-330">In the **Chart Title Properties** dialog box, in Title text, type: **Product Quantities Sold**.</span></span>

12. <span data-ttu-id="b2e2e-331">Перейдите на вкладку **Шрифт** и в списке **Размер** выберите **10пт**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-331">Click the **Font** tab, and in the **Size** list, click **10pt**.</span></span>

13. [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-column-chart"></a><span data-ttu-id="b2e2e-332">Добавление гистограммы</span><span class="sxs-lookup"><span data-stu-id="b2e2e-332">To add a column chart</span></span>

1.  <span data-ttu-id="b2e2e-333">На вкладке **Вставка** ленты в области **Визуализации данных** нажмите **Диаграмма** , затем — **Мастер диаграмм**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-333">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="b2e2e-334">На странице **Выбор набора данных** нажмите **ListDataset**, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-334">On the **Choose a dataset** page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="b2e2e-335">Выберите **Столбец**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-335">Click **Column**, and then click **Next**.</span></span>

4.  <span data-ttu-id="b2e2e-336">На странице Расположение полей диаграммы перетащите поле Product в **категории**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-336">On the arrange chart fields page, drag the Product field to **Categories**.</span></span>

5.  <span data-ttu-id="b2e2e-337">Перетащите поле Sales в **Значения** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-337">Drag Sales to **Values,** and then click **Next**.</span></span>

     <span data-ttu-id="b2e2e-338">Значения отображаются по вертикальной оси.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-338">Values display on the vertical axis.</span></span>

6.  <span data-ttu-id="b2e2e-339">На странице **Выбор стиля** панели **Стили** выберите **Сланец**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-339">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="b2e2e-340">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-340">Click **Finish**.</span></span>

     <span data-ttu-id="b2e2e-341">Гистограмма добавляется в верхний левый угол отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-341">A column chart is added to the upper left corner of the report.</span></span>

8.  <span data-ttu-id="b2e2e-342">Измените размеры диаграммы, установив ширину 2 дюйма и высоту 2 дюйма.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-342">Resize the chart to be 2 inches wide and 2 inches tall.</span></span>

9. <span data-ttu-id="b2e2e-343">Перетащите диаграмму внутрь прямоугольника ниже круговой диаграммы.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-343">Drag the chart inside the rectangle, below the pie chart.</span></span>

     <span data-ttu-id="b2e2e-344">![Добавление гистограммы](../../2014/tutorials/media/tutorial-addcolumnchart.png "Добавление гистограммы")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-344">![Add column chart](../../2014/tutorials/media/tutorial-addcolumnchart.png "Add column chart")</span></span>

10. <span data-ttu-id="b2e2e-345">Щелкните правой кнопкой мыши заголовок диаграммы и выберите пункт **Свойства заголовка**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-345">Right-click the chart title and then click **Title Properties**.</span></span>

11. <span data-ttu-id="b2e2e-346">В диалоговом окне **Свойства заголовка диаграммы** в поле «Текст заголовка» введите **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-346">In the **Chart Title Properties** dialog box, in Title text, type: **Product Sales**.</span></span>

12. <span data-ttu-id="b2e2e-347">Нажмите вкладку **Шрифт** , в списке **Размер** выберите **10 пт**и нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-347">Click the **Font** tab, and in the **Size** list click **10pt**, and then click **OK**.</span></span>

13. <span data-ttu-id="b2e2e-348">На диаграмме щелкните правой кнопкой мыши вертикальную ось, а затем снимите флажок **Показывать название оси**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-348">In the column chart, right click the vertical axis, and then deselect **Show Axis Title**.</span></span>

14. <span data-ttu-id="b2e2e-349">Повторите пункт 13 для горизонтальной оси.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-349">Repeat step 13 for the horizontal axis.</span></span>

15. <span data-ttu-id="b2e2e-350">Щелкните правой кнопкой мыши условные обозначения и выберите команду **Удалить условные обозначения**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-350">Right click the legend, and then click **Delete Legend**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-351">После удаления заголовков осей и условных обозначений становится удобнее читать диаграммы малого размера.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-351">Removing axis titles and the legend makes the chart more readable when it is a small size.</span></span>

 <span data-ttu-id="b2e2e-352">![Изменение названий диаграмм и удаление названия оси](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Изменение названий диаграмм и удаление названия оси")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-352">![Change chart titles and remove axis title](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Change chart titles and remove axis title")</span></span>

#### <a name="to-verify-the-charts-are-inside-the-rectangle"></a><span data-ttu-id="b2e2e-353">Проверка местонахождения диаграмм внутри прямоугольника</span><span class="sxs-lookup"><span data-stu-id="b2e2e-353">To verify the charts are inside the rectangle</span></span>

1.  <span data-ttu-id="b2e2e-354">Щелкните ранее добавленный в этом уроке прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-354">Click the rectangle you added earlier in this lesson.</span></span>

     <span data-ttu-id="b2e2e-355">Свойство `Name` на панели «Свойства» показывает имя прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-355">In the Properties pane, the `Name` property displays the name of the rectangle.</span></span>

     <span data-ttu-id="b2e2e-356">![Имя прямоугольника](../../2014/tutorials/media/tutorial-rectanglename.png "Имя прямоугольника")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-356">![Name of rectangle](../../2014/tutorials/media/tutorial-rectanglename.png "Name of rectangle")</span></span>

2.  <span data-ttu-id="b2e2e-357">Щелкните круговую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-357">Click the pie chart.</span></span>

3.  <span data-ttu-id="b2e2e-358">В области **Свойства** убедитесь, что `Parent` свойство содержит имя прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-358">In the **Properties** pane, verify that the `Parent` property contains the name of the rectangle.</span></span>

     <span data-ttu-id="b2e2e-359">![Родительское свойство для круговой диаграммы](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Родительское свойство для круговой диаграммы")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-359">![Parent property for pie chart](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Parent property for pie chart")</span></span>

4.  <span data-ttu-id="b2e2e-360">Нажмите гистограмму и повторите пункты 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-360">Click the column chart and repeat steps 2 and 3.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-361">Если диаграммы не находятся внутри прямоугольника, то не отображаются вместе в подготовленном к просмотру отчете.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-361">If the charts are not inside the rectangle, the rendered report does not display the charts together.</span></span>

#### <a name="to-make-the-charts-the-same-size"></a><span data-ttu-id="b2e2e-362">Придание одинаковых размеров диаграммам</span><span class="sxs-lookup"><span data-stu-id="b2e2e-362">To make the charts the same size</span></span>

1.  <span data-ttu-id="b2e2e-363">Щелкните круговую диаграмму, нажмите клавишу Ctrl, а затем щелкните гистограмму.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-363">Click the pie chart, press the Ctrl key, and then click the column chart.</span></span>

2.  <span data-ttu-id="b2e2e-364">Выделив обе диаграммы, щелкните правой кнопкой мыши, укажите **Макет**и выберите команду **Установить ту же ширину**.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-364">With both charts selected, right-click, point to **Layout**, and then click **Make Same Width**.</span></span>

     <span data-ttu-id="b2e2e-365">![Придание одинаковой ширины диаграмме](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Придание одинаковой ширины диаграмме")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-365">![Make chart widths the same](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Make chart widths the same")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b2e2e-366">Элемент, который вы щелкнули сначала, задает ширину для всех выбранных элементов.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-366">The item you click first determines the width of all the selected items.</span></span>

3.  <span data-ttu-id="b2e2e-367">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-367">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b2e2e-368">Теперь отчет содержит сводные данные о продажах в круговых диаграммах и гистограммах.</span><span class="sxs-lookup"><span data-stu-id="b2e2e-368">The report now displays summary sales data in pie and column charts.</span></span>

 <span data-ttu-id="b2e2e-369">![Учебник по службам SSRS, отчет произвольной формы](../../2014/tutorials/media/tutorial-reportfinal.png "Учебник по службам SSRS, отчет произвольной формы")</span><span class="sxs-lookup"><span data-stu-id="b2e2e-369">![SSRS tutorial, free form report](../../2014/tutorials/media/tutorial-reportfinal.png "SSRS tutorial, free form report")</span></span>

## <a name="more-information"></a><span data-ttu-id="b2e2e-370">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b2e2e-370">More Information</span></span>
 <span data-ttu-id="b2e2e-371">Дополнительные сведения о списках см. в разделах [таблицы, матрицы и списки &#40;построитель отчетов и службы ssrs&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [списки &#40;построитель отчетов и SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [области данных табликса &#40;построитель отчетов и SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)и [ячейки, строки и столбцы области данных табликса &#40;построитель отчетов&#41; и SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b2e2e-371">For more information about lists, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="b2e2e-372">Дополнительные сведения о конструкторах запросов см. в разделах [Конструкторы запросов (построитель отчетов)](../../2014/reporting-services/query-designers-report-builder.md) и [Пользовательский интерфейс текстового конструктора запросов (построитель отчетов)](report-data/text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b2e2e-372">For more information about query designers, see [Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) and [Text-based Query Designer User Interface &#40;Report Builder&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2e2e-373">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2e2e-373">See Also</span></span>
 <span data-ttu-id="b2e2e-374">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) [построитель отчетов в SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="b2e2e-374">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span></span>


