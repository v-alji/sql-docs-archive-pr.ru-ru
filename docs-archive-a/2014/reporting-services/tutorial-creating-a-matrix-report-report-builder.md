---
title: Учебник. Создание матричного отчета (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9ee19c2e-2a8c-4bb0-9274-04a5812c2e96
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3df32098d9e6400931ba2a88b2ffd22d6e015a62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737820"
---
# <a name="tutorial-creating-a-matrix-report-report-builder"></a><span data-ttu-id="30ac0-102">Учебник. Создание матричного отчета (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="30ac0-102">Tutorial: Creating a Matrix Report (Report Builder)</span></span>
  <span data-ttu-id="30ac0-103">Это учебник поможет создать простой матричный отчет на основе образца данных по продажам.</span><span class="sxs-lookup"><span data-stu-id="30ac0-103">This tutorial teaches you how to create a basic matrix report based on sample sales data.</span></span> <span data-ttu-id="30ac0-104">Матрица имеет вложенные группы строк и столбцов и смежную группу столбцов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-104">The matrix has nested row and column groups and an adjacent column group.</span></span> <span data-ttu-id="30ac0-105">Вы узнаете, как форматировать столбцы и поворачивать текст.</span><span class="sxs-lookup"><span data-stu-id="30ac0-105">You will also learn how to format columns and rotate text.</span></span> <span data-ttu-id="30ac0-106">На приведенном далее рисунке показан отчет, похожий на тот, который будет в итоге создан.</span><span class="sxs-lookup"><span data-stu-id="30ac0-106">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="30ac0-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="30ac0-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span></span>  
  
 <span data-ttu-id="30ac0-108">Улучшенная версия отчета, который будет создан в этом учебнике, доступна в качестве образца отчета в построителе отчетов [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30ac0-108">An enhanced version of the report you will create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="30ac0-109">Дополнительные сведения о загрузке этого и других образцов отчетов см. в разделе [Образцы отчетов построителя отчетов](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="30ac0-109">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="30ac0-110">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="30ac0-110">What You Will Learn</span></span>  
 <span data-ttu-id="30ac0-111">В этом учебнике рассматривается следующее.</span><span class="sxs-lookup"><span data-stu-id="30ac0-111">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="30ac0-112">Создание матричного отчета и набора данных с помощью мастера новой таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-112">Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>](#CreateMatrix)  
  
2.  [<span data-ttu-id="30ac0-113">Организация данных, выбор макета и стиля в мастере новой таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-113">Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>](#Groups)  
  
3.  [<span data-ttu-id="30ac0-114">Форматирование данных</span><span class="sxs-lookup"><span data-stu-id="30ac0-114">Format Data</span></span>](#FormatData)  
  
4.  [<span data-ttu-id="30ac0-115">Добавление смежной группы столбцов</span><span class="sxs-lookup"><span data-stu-id="30ac0-115">Add Adjacent Column Group</span></span>](#AdjacentGroup)  
  
5.  [<span data-ttu-id="30ac0-116">Изменение ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="30ac0-116">Change Column Widths</span></span>](#Width)  
  
6.  [<span data-ttu-id="30ac0-117">Объединение ячеек матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-117">Merge Matrix Cells</span></span>](#MergeCells)  
  
7.  [<span data-ttu-id="30ac0-118">Добавление верхнего колонтитула и заголовка в отчет</span><span class="sxs-lookup"><span data-stu-id="30ac0-118">Add a Report Header and Report Title</span></span>](#HeaderTitle)  
  
8.  [<span data-ttu-id="30ac0-119">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="30ac0-119">Save the Report</span></span>](#Save)  
  
### <a name="other-optional-step"></a><span data-ttu-id="30ac0-120">Другие дополнительные шаги</span><span class="sxs-lookup"><span data-stu-id="30ac0-120">Other Optional Step</span></span>  
  
1.  [<span data-ttu-id="30ac0-121">Поворот текстового поля на 270 градусов</span><span class="sxs-lookup"><span data-stu-id="30ac0-121">Rotate Text Box 270 Degrees</span></span>](#RotateTextBox)  
  
 <span data-ttu-id="30ac0-122">Предполагаемое время для выполнения заданий данного учебника: 20 минут</span><span class="sxs-lookup"><span data-stu-id="30ac0-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30ac0-123">Требования</span><span class="sxs-lookup"><span data-stu-id="30ac0-123">Requirements</span></span>  
 <span data-ttu-id="30ac0-124">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="30ac0-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-new-table-or-matrix-wizard"></a><a name="CreateMatrix"></a><span data-ttu-id="30ac0-125">1. Создание матричного отчета и набора данных с помощью мастера создания таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-125">1. Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="30ac0-126">В диалоговом окне **Начало работы** в построитель отчетов выберите общий источник данных, создайте внедренный набор данных, а затем отобразите данные в матрице.</span><span class="sxs-lookup"><span data-stu-id="30ac0-126">From the **Getting Started** dialog box in Report Builder, choose a shared data source, create an embedded dataset, and then display the data in a matrix.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30ac0-127">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="30ac0-127">In this tutorial, the query already contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="30ac0-128">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="30ac0-128">This makes the query quite long.</span></span> <span data-ttu-id="30ac0-129">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="30ac0-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="30ac0-130">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="30ac0-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix"></a><span data-ttu-id="30ac0-131">Создание новой матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-131">To create a new matrix</span></span>  
  
1.  <span data-ttu-id="30ac0-132">Нажмите кнопку **Пуск**, наведите курсор на пункты **Все программы**, **Построитель отчетов Microsoft SQL Server 2012**и выберите пункт **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30ac0-133">Должно открыться диалоговое окно **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-133">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="30ac0-134">В противном случае нажмите кнопку " **создать**" в построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-134">If it doesn't, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="30ac0-135">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="30ac0-136">На панели справа выберите **Мастер таблицы или матрицы**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="30ac0-137">На странице **Выбор набора данных** выберите **Создать набор данных**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-137">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="30ac0-138">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="30ac0-139">На странице **Выбор соединения с источником данных** выберите существующий источник данных или перейдите к серверу отчетов, а затем выберите источник данных.</span><span class="sxs-lookup"><span data-stu-id="30ac0-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server, and then select a data source.</span></span> <span data-ttu-id="30ac0-140">Если отсутствуют доступные источники данных или доступ к серверу отчетов, можно воспользоваться внедренным источником данных.</span><span class="sxs-lookup"><span data-stu-id="30ac0-140">If no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="30ac0-141">Дополнительные сведения о создании внедренного источника данных см. [в разделе Учебник. Создание простого табличного отчета &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="30ac0-141">For more information about creating an embedded data source, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="30ac0-142">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="30ac0-143">На странице **Проектирование запроса** нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="30ac0-144">Скопируйте и вставьте на панели запросов следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="30ac0-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity  
    ```  
  
10. <span data-ttu-id="30ac0-145">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-and-choose-layout-and-style-from-the-new-table-or-matrix-wizard"></a><a name="Groups"></a><span data-ttu-id="30ac0-146">2. Организация данных и выбор макета и стиля в мастере создания таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-146">2. Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="30ac0-147">С помощью мастера начните конструировать отчет, в котором будут отображаться данные.</span><span class="sxs-lookup"><span data-stu-id="30ac0-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="30ac0-148">Панель предварительного просмотра в мастере позволяет визуально представить результат группирования данных до завершения конструирования матрицы.</span><span class="sxs-lookup"><span data-stu-id="30ac0-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-and-choose-a-layout-and-style"></a><span data-ttu-id="30ac0-149">Разбиение данных по группам и выбор макета и стиля</span><span class="sxs-lookup"><span data-stu-id="30ac0-149">To organize data into groups and choose a layout and style</span></span>  
  
1.  <span data-ttu-id="30ac0-150">На странице **Размещение полей** перетащите поле "Территория" из области **Доступные поля** в область **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-150">On the **Arrange fields** page, drag Territory from **Available fields** to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="30ac0-151">Перетащите поле SalesDate в **Группы строк** и поместите ниже поля "Территория".</span><span class="sxs-lookup"><span data-stu-id="30ac0-151">Drag SalesDate to **Row groups** and place it below Territory.</span></span>  
  
     <span data-ttu-id="30ac0-152">Порядок, в котором поля перечислены в области **Группы строк** , определяет иерархию группы.</span><span class="sxs-lookup"><span data-stu-id="30ac0-152">The order in which fields are listed in **Row groups** defines the group hierarchy.</span></span> <span data-ttu-id="30ac0-153">Шаги 1 и 2 организуют значения полей сначала по территории, а затем по дате продажи.</span><span class="sxs-lookup"><span data-stu-id="30ac0-153">Steps 1 and 2 organize the values of the fields first by territory, and then by sales date.</span></span>  
  
3.  <span data-ttu-id="30ac0-154">Перетащите поле "Подкатегория" в область **Группы столбцов**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-154">Drag Subcategory to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="30ac0-155">Перетащите Product в **группы столбцов,** а затем поместите под подкатегорией.</span><span class="sxs-lookup"><span data-stu-id="30ac0-155">Drag Product to **Column groups,** and then place below Subcategory.</span></span>  
  
     <span data-ttu-id="30ac0-156">Порядок, в котором поля перечислены в **группах столбцов** , определяет иерархию групп.</span><span class="sxs-lookup"><span data-stu-id="30ac0-156">The order in which fields are listed in **Column groups** defines the group hierarchy.</span></span>  
  
     <span data-ttu-id="30ac0-157">Шаги 3 и 4 организуют значения полей сначала по подкатегории, а затем по продукту.</span><span class="sxs-lookup"><span data-stu-id="30ac0-157">Steps 3 and 4 organize the values for the fields first by subcategory, and then by product.</span></span>  
  
5.  <span data-ttu-id="30ac0-158">Перетащите поле "Продажи" в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-158">Drag Sales to **Values**.</span></span>  
  
     <span data-ttu-id="30ac0-159">Сводные значения для поля Sales вычисляются с помощью функции Sum, которая является функцией по умолчанию для вычисления сводных значений числовых полей.</span><span class="sxs-lookup"><span data-stu-id="30ac0-159">Sales is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
6.  <span data-ttu-id="30ac0-160">Перетащите поле "Количество" в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-160">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="30ac0-161">Сводные значения для поля Quantity вычисляются с помощью функции Sum.</span><span class="sxs-lookup"><span data-stu-id="30ac0-161">Quantity is summarized with the Sum function.</span></span>  
  
     <span data-ttu-id="30ac0-162">Шаги 5 и 6 задают данные, отображаемые в ячейках данных матрицы.</span><span class="sxs-lookup"><span data-stu-id="30ac0-162">Steps 5 and 6 specify the data to display in the matrix data cells.</span></span>  
  
7.  <span data-ttu-id="30ac0-163">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-163">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="30ac0-164">Убедитесь в том, что на странице "Выбор макета" в области **Параметры**выбран параметр **Показывать подытоги и общие итоги** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-164">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
9. <span data-ttu-id="30ac0-165">Убедитесь в том, что выбран параметр **Заблокированный, подытог ниже** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-165">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
10. <span data-ttu-id="30ac0-166">Убедитесь в том, что установлен флажок **Развернуть или свернуть группы** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-166">Verify the option **Expand/collapse groups** is selected.</span></span>  
  
11. <span data-ttu-id="30ac0-167">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-167">Click **Next**.</span></span>  
  
12. <span data-ttu-id="30ac0-168">На странице Выбор стиля панели Стили выберите **Сланец**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-168">On the Choose a Style page, in the Styles pane, select **Slate**.</span></span>  
  
13. <span data-ttu-id="30ac0-169">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-169">Click **Finish**.</span></span>  
  
     <span data-ttu-id="30ac0-170">Матрица добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="30ac0-170">The matrix is added to the design surface.</span></span> <span data-ttu-id="30ac0-171">Панель «Группы строк» показывает две группы строк: Territory и SalesDate.</span><span class="sxs-lookup"><span data-stu-id="30ac0-171">The Row Groups pane shows two row groups: Territory and SalesDate.</span></span> <span data-ttu-id="30ac0-172">Панель «Группы столбцов» отображает две группы столбцов: Subcategory и Product.</span><span class="sxs-lookup"><span data-stu-id="30ac0-172">The Column Groups pane shows two column groups: Subcategory and Product.</span></span> <span data-ttu-id="30ac0-173">Подробные данные — это все данные, которые извлекаются с помощью запроса к набору данных.</span><span class="sxs-lookup"><span data-stu-id="30ac0-173">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
14. <span data-ttu-id="30ac0-174">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-174">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="30ac0-175">Для каждого продукта, проданного за указанную дату, в матрице отображается подкатегория, к которой принадлежит продукт, и территория продаж.</span><span class="sxs-lookup"><span data-stu-id="30ac0-175">For each product that is sold on a specific date, the matrix shows the subcategory to which the product belongs and the territory of the sales.</span></span>  
  
##  <a name="3-format-data"></a><a name="FormatData"></a><span data-ttu-id="30ac0-176">3. Форматирование данных</span><span class="sxs-lookup"><span data-stu-id="30ac0-176">3. Format Data</span></span>  
 <span data-ttu-id="30ac0-177">По умолчанию сводные данные поля Sales отображаются в виде числа с общим форматом, а поле SalesDate содержит сведения как о дате, так и о времени.</span><span class="sxs-lookup"><span data-stu-id="30ac0-177">By default, the summary data for the Sales field displays a general number and the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="30ac0-178">Отформатируйте поле Sales, чтобы отображать число для представления денежных значений, а поле SalesDate — сведений только о дате.</span><span class="sxs-lookup"><span data-stu-id="30ac0-178">Format the Sales field to display the number as currency and the SalesDate field to display only the date.</span></span> <span data-ttu-id="30ac0-179">Чтобы форматируемые текстовые поля и текст заполнителей отображался в виде образцов значений, переключайте параметр **Стили заполнителя** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-179">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-fields"></a><span data-ttu-id="30ac0-180">Форматирование полей</span><span class="sxs-lookup"><span data-stu-id="30ac0-180">To format fields</span></span>  
  
1.  <span data-ttu-id="30ac0-181">Нажмите кнопку **конструктор** , чтобы перейти в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="30ac0-181">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="30ac0-182">Нажмите клавишу Ctrl, а затем выберите девять ячеек, содержащих `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="30ac0-182">Press the Ctrl key, and then select the nine cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="30ac0-183">На вкладке **Главная** в группе **Число** нажмите кнопку **Валюта**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-183">On the **Home** tab, in the **Number** group, click **Currency**.</span></span> <span data-ttu-id="30ac0-184">Ячейки изменятся, отображая содержимое в формате валюты.</span><span class="sxs-lookup"><span data-stu-id="30ac0-184">The cells changeto show the formatted currency.</span></span>  
  
     <span data-ttu-id="30ac0-185">Если в качестве региональных настроек компьютера выбран "Английский (США)", текстом по умолчанию образца будет [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="30ac0-185">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="30ac0-186">Если значение валюты не отображается, щелкните ссылку **Стили заполнителя** в группе **Числа** , а затем нажмите кнопку **Образцы значений**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-186">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="30ac0-187">Щелкните ячейку, содержащую `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="30ac0-187">Click the cell that contains `[SalesDate]`.</span></span>  
  
5.  <span data-ttu-id="30ac0-188">В раскрывающемся списке Группа **число** выберите **Дата**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-188">In the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="30ac0-189">В ячейке отображается пример даты **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-189">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="30ac0-190">Если дата не отображается, щелкните ссылку **Стили заполнителя** в группе **Числа** , а затем нажмите кнопку **Образцы значений**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-190">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
6.  <span data-ttu-id="30ac0-191">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-191">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="30ac0-192">Значения дат отображают только даты, а значения продаж представлены в денежном формате.</span><span class="sxs-lookup"><span data-stu-id="30ac0-192">The date values display only dates and the sales values display as currency.</span></span>  
  
##  <a name="4-add-adjacent-column-group"></a><a name="AdjacentGroup"></a><span data-ttu-id="30ac0-193">4. Добавление смежной группы столбцов</span><span class="sxs-lookup"><span data-stu-id="30ac0-193">4. Add Adjacent Column Group</span></span>  
 <span data-ttu-id="30ac0-194">Можно внедрить группы строк и столбцов в связи «родители-потомки», а смежные группы — в одноранговые связи.</span><span class="sxs-lookup"><span data-stu-id="30ac0-194">You can nest row and column groups in parent child relationships or adjacent in sibling relationships.</span></span>  
  
 <span data-ttu-id="30ac0-195">Добавьте смежную группу столбцов в группу столбцов Subcategory, скопируйте ячейки, чтобы заполнить новую группу столбцов, и используйте выражение для создания значения заголовка группы столбцов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-195">Add a column group that is adjacent to the Subcategory column group, copy cells to populate the new column group, and then use an expression to create the value of the column group header.</span></span>  
  
#### <a name="to-add-an-adjacent-column-group"></a><span data-ttu-id="30ac0-196">Добавление смежной группы столбцов</span><span class="sxs-lookup"><span data-stu-id="30ac0-196">To add an adjacent column group</span></span>  
  
1.  <span data-ttu-id="30ac0-197">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="30ac0-197">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="30ac0-198">Щелкните правой кнопкой мыши ячейку, которая содержит `[Subcategory]`, наведите указатель на пункт **Добавить группу**и выберите пункт **Прилегающая справа**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-198">Right-click the cell that contains `[Subcategory]`, point to **Add Group**, and then click **Adjacent Right**.</span></span>  
  
     <span data-ttu-id="30ac0-199">Откроется диалоговое окно **Группа табликсов** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-199">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="30ac0-200">В списке **Группировать** выберите SalesDate и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-200">In the **Group By** list, select SalesDate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="30ac0-201">Новая группа столбцов будет добавлена слева от группы столбцов Subcategory.</span><span class="sxs-lookup"><span data-stu-id="30ac0-201">A new column group is added to the left of the Subcategory column group.</span></span>  
  
4.  <span data-ttu-id="30ac0-202">Щелкните правой кнопкой мыши ячейку в новой группе столбцов, которая содержит `[SalesDate],` , а затем выберите пункт **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-202">Right-click the cell in the new column group that contains `[SalesDate],` and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="30ac0-203">В поле «Выражение» скопируйте следующее выражение.</span><span class="sxs-lookup"><span data-stu-id="30ac0-203">Copy the following expression to expression box.</span></span>  
  
    ```  
    =WeekdayName(DatePart("w",Fields!SalesDate.Value))  
    ```  
  
     <span data-ttu-id="30ac0-204">Это выражение извлекает день недели из данных о продажах.</span><span class="sxs-lookup"><span data-stu-id="30ac0-204">This expression extracts the weekday name from the sales date.</span></span> <span data-ttu-id="30ac0-205">Дополнительные сведения см. в разделе [Выражения (построитель отчетов и службы SSRS)](report-design/expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="30ac0-205">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="30ac0-206">Щелкните правой кнопкой мыши ячейку в группе столбцов "Подкатегория", которая содержит итог, а затем выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-206">Right-click the cell in the Subcategory column group that contains Total, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="30ac0-207">Щелкните правой кнопкой мыши ячейку, которая находится непосредственно под ячейкой, содержащей выражение, созданное в шаге 5, и выберите пункт **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-207">Right-click the cell immediately below the cell that contains the expression you created in step 5 and click **Paste**.</span></span>  
  
8.  <span data-ttu-id="30ac0-208">Нажмите клавишу Ctrl.</span><span class="sxs-lookup"><span data-stu-id="30ac0-208">Press the Ctrl key.</span></span>  
  
9. <span data-ttu-id="30ac0-209">В группе "Подкатегория" щелкните правой кнопкой мыши заголовок столбца "Продажи" и три ячейки под ним, а затем выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-209">In the Subcategory group, click the Sales column header and the three cells below it, right-click, and then click **Copy**.</span></span>  
  
10. <span data-ttu-id="30ac0-210">Вставьте четыре ячейки в четыре пустые ячейки в новой группе столбцов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-210">Paste the four cells into the four empty cells in the new column group.</span></span>  
  
11. <span data-ttu-id="30ac0-211">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-211">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="30ac0-212">Отчет включает столбцы с именами Monday и Tuesday.</span><span class="sxs-lookup"><span data-stu-id="30ac0-212">The report includes columns named Monday and Tuesday.</span></span> <span data-ttu-id="30ac0-213">Набор данных содержит данные только для этих двух дней.</span><span class="sxs-lookup"><span data-stu-id="30ac0-213">The dataset contains only data for these two days.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30ac0-214">Если бы данные охватывали другие дни, в отчет вошли бы столбцы и для них.</span><span class="sxs-lookup"><span data-stu-id="30ac0-214">If the data included other days, the report would include columns for them as well.</span></span> <span data-ttu-id="30ac0-215">Каждый столбец содержит заголовок столбца, `Sales` и итоги продаж по территориям.</span><span class="sxs-lookup"><span data-stu-id="30ac0-215">Each column has the column header, `Sales`, and sales totals by territory.</span></span>  
  
##  <a name="5-change-column-widths"></a><a name="Width"></a><span data-ttu-id="30ac0-216">5. изменение ширины столбцов</span><span class="sxs-lookup"><span data-stu-id="30ac0-216">5. Change Column Widths</span></span>  
 <span data-ttu-id="30ac0-217">Отчет, содержащий матрицу, при выполнении обычно расширяется как по горизонтали, так и по вертикали.</span><span class="sxs-lookup"><span data-stu-id="30ac0-217">A report that includes a matrix typically expands horizontally as well as vertically when it runs.</span></span> <span data-ttu-id="30ac0-218">Особенно важно управлять расширением по горизонтали, если планируется экспортировать форматы наподобие Microsoft Word или Adobe PDF для создания печатных отчетов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-218">Controlling horizontal expansion is particularly important if you plan to export the report to formats such as Microsoft Word or Adobe PDF that are used for printed reports.</span></span> <span data-ttu-id="30ac0-219">Если отчет расширяется по горизонтали на несколько страниц, то понять печатный отчет сложно.</span><span class="sxs-lookup"><span data-stu-id="30ac0-219">If the report expands horizontally across multiple pages, the printed report is difficult to understand.</span></span> <span data-ttu-id="30ac0-220">Чтобы уменьшить горизонтальное расширение, можно изменить размеры столбцов до ширины, необходимой для отображения данных без переносов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-220">To minimize horizontal expansion, you can resize columns to be only the width necessary to display the data without wrapping.</span></span> <span data-ttu-id="30ac0-221">Можно также переименовать столбцы, чтобы их заголовки соответствовали ширине, необходимой для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="30ac0-221">You can also rename columns so that their titles fit the width needed to display the data.</span></span>  
  
#### <a name="to-rename-and-resize-the-columns"></a><span data-ttu-id="30ac0-222">Изменение имени и размера столбцов</span><span class="sxs-lookup"><span data-stu-id="30ac0-222">To rename and resize the columns</span></span>  
  
1.  <span data-ttu-id="30ac0-223">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="30ac0-223">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="30ac0-224">Выделите текст в крайнем левом столбце "Количество" и введите **Кол-во**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-224">Select the text in the furthest Quantity column to the left, and then type **QTY**.</span></span>  
  
     <span data-ttu-id="30ac0-225">Теперь заголовок столбца — "Кол-во".</span><span class="sxs-lookup"><span data-stu-id="30ac0-225">The column title is now QTY.</span></span>  
  
3.  <span data-ttu-id="30ac0-226">Повторите шаг 2 для других столбцов с именем Quantity.</span><span class="sxs-lookup"><span data-stu-id="30ac0-226">Repeat step 2 for the other columns named Quantity.</span></span> <span data-ttu-id="30ac0-227">Их два.</span><span class="sxs-lookup"><span data-stu-id="30ac0-227">There are two of them.</span></span>  
  
4.  <span data-ttu-id="30ac0-228">Щелкните матрицу, чтобы сбоку и сверху от нее появились маркеры строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-228">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
     <span data-ttu-id="30ac0-229">Серые линии, расположенные вдоль верха и стороны таблицы, — это маркеры столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="30ac0-229">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
5.  <span data-ttu-id="30ac0-230">Чтобы изменить размер самого дальнего столбца QTY слева, укажите линию раздела между маркерами столбцов, чтобы курсор принял вид двойной стрелки.</span><span class="sxs-lookup"><span data-stu-id="30ac0-230">To resize the furthest QTY column to the left, point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="30ac0-231">Перетаскивайте столбец влево, пока его ширина не станет равной 1/2 дюйма.</span><span class="sxs-lookup"><span data-stu-id="30ac0-231">Drag the column towards the left until it is 1/2 inch wide.</span></span>  
  
     <span data-ttu-id="30ac0-232">Ширина столбца 1/2 дюйма достаточна для отображения количества.</span><span class="sxs-lookup"><span data-stu-id="30ac0-232">A column width of 1/2 inch is adequate to display the quantity.</span></span>  
  
6.  <span data-ttu-id="30ac0-233">Повторите шаг 5 для других столбцов с именем QTY.</span><span class="sxs-lookup"><span data-stu-id="30ac0-233">Repeat step 5 for the other columns named QTY.</span></span>  
  
7.  <span data-ttu-id="30ac0-234">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-234">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="30ac0-235">Столбцы в этом отчете, содержащие сведения о количестве, теперь имеют имя QTY, и их ширина стала меньше.</span><span class="sxs-lookup"><span data-stu-id="30ac0-235">The columns in the report that contains quantities are now named QTY and the columns are narrower.</span></span>  
  
##  <a name="6-merge-matrix-cells"></a><a name="MergeCells"></a><span data-ttu-id="30ac0-236">6. Объединение ячеек матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-236">6. Merge Matrix Cells</span></span>  
 <span data-ttu-id="30ac0-237">Область угла находится в левом верхнем углу матрицы.</span><span class="sxs-lookup"><span data-stu-id="30ac0-237">The corner area is in the upper left corner of the matrix.</span></span> <span data-ttu-id="30ac0-238">В зависимости от числа групп строк и столбцов в матрице, число ячеек в области угла может быть различным.</span><span class="sxs-lookup"><span data-stu-id="30ac0-238">Depending on the number of row and column groups in the matrix, the number of cells in the corner area varies.</span></span> <span data-ttu-id="30ac0-239">У матрицы, построенной в этом учебнике, в области угла находятся четыре ячейки.</span><span class="sxs-lookup"><span data-stu-id="30ac0-239">The matrix, built in this tutorial, has four cells in its corner area.</span></span> <span data-ttu-id="30ac0-240">Ячейки организованы в две строки и два столбца, в соответствии с глубиной иерархий групп строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-240">The cells are arranged in two rows and two columns, reflecting the depth of row and column group hierarchies.</span></span> <span data-ttu-id="30ac0-241">Четыре ячейки не используются в этом отчете, и будет выполнено их объединение в одну ячейку.</span><span class="sxs-lookup"><span data-stu-id="30ac0-241">The four cells are not used in this report and you will merge them into one.</span></span>  
  
#### <a name="to-merge-matrix-cells"></a><span data-ttu-id="30ac0-242">Объединение ячеек матрицы</span><span class="sxs-lookup"><span data-stu-id="30ac0-242">To merge matrix cells</span></span>  
  
1.  <span data-ttu-id="30ac0-243">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="30ac0-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="30ac0-244">Щелкните матрицу, чтобы сбоку и сверху от нее появились маркеры строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-244">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
3.  <span data-ttu-id="30ac0-245">Нажмите клавишу Ctrl, а затем выберите четыре угловые ячейки.</span><span class="sxs-lookup"><span data-stu-id="30ac0-245">Press the Ctrl key, and then select the four corner cells.</span></span>  
  
4.  <span data-ttu-id="30ac0-246">Щелкните правой кнопкой мыши ячейки и выберите команду **объединить ячейки**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-246">Right-click the cells and then click **Merge Cells**.</span></span>  
  
5.  <span data-ttu-id="30ac0-247">Щелкните правой кнопкой мыши угловую ячейку и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-247">Right-click the corner cell, and then click **Text Box Properties**.</span></span>  
  
6.  <span data-ttu-id="30ac0-248">Перейдите на вкладку **Заливка** .</span><span class="sxs-lookup"><span data-stu-id="30ac0-248">Click the **Fill** tab.</span></span>  
  
7.  <span data-ttu-id="30ac0-249">Нажмите кнопку (***FX***), чтобы выбрать **Цвет заливки**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-249">Click the (***fx***) button for **Fill color**.</span></span>  
  
8.  <span data-ttu-id="30ac0-250">Скопируйте и вставьте следующее выражение в поле «Выражение».</span><span class="sxs-lookup"><span data-stu-id="30ac0-250">Copy and paste the following expression in the expression box.</span></span>  
  
    ```  
    #96a4b2  
    ```  
  
     <span data-ttu-id="30ac0-251">Это шестнадцатеричное значение RGB для синевато-серого цвета, используемого в стиле «Сланец».</span><span class="sxs-lookup"><span data-stu-id="30ac0-251">This is the RGB hex value for a gray blue color used in the Slate style.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="30ac0-252">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-252">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="30ac0-253">Верхний угол матрицы представляет собой единственную ячейку и имеет такой же цвет, как ячейки группы строк и группы столбцов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-253">The upper corner matrix is a single cell and has the same color as the row group and column group cells.</span></span>  
  
##  <a name="7-add-a-report-header-and-report-title"></a><a name="HeaderTitle"></a><span data-ttu-id="30ac0-254">7. Добавление заголовка отчета и заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="30ac0-254">7. Add a Report Header and Report Title</span></span>  
 <span data-ttu-id="30ac0-255">Заголовок отчета отображается в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-255">A report title appears at the top of the report.</span></span> <span data-ttu-id="30ac0-256">Можно поместить заголовок отчета в верхнем колонтитуле или, если в отчете колонтитулы не используются, в текстовом поле в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-256">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="30ac0-257">В данном учебнике будет удалено текстовое поле в верхней части отчета и добавлен заголовок в верхний колонтитул.</span><span class="sxs-lookup"><span data-stu-id="30ac0-257">In this tutorial, you will remove the text box at the top of the report and add a title to the header.</span></span>  
  
#### <a name="to-add-a-report-header-and-report-title"></a><span data-ttu-id="30ac0-258">Добавление верхнего колонтитула и заголовка в отчет</span><span class="sxs-lookup"><span data-stu-id="30ac0-258">To add a report header and report title</span></span>  
  
1.  <span data-ttu-id="30ac0-259">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="30ac0-259">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="30ac0-260">Щелкните текстовое поле в верхней части текста отчета, содержащего **щелкните, чтобы добавить заголовок**, а затем нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="30ac0-260">Click the text box at the top of the report body that contains **Click to add title**, and then press the Delete key.</span></span>  
  
3.  <span data-ttu-id="30ac0-261">На вкладке ленты **Вставка** щелкните **заголовок** , а затем щелкните **Добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-261">On the **Insert** tab of the ribbon, click **Header** and then click **Add Header**.</span></span>  
  
     <span data-ttu-id="30ac0-262">Верхний колонтитул добавляется в верхнюю часть текста отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-262">A header is added to the top of the report body.</span></span>  
  
4.  <span data-ttu-id="30ac0-263">На вкладке **Вставка** щелкните **Текстовое поле**, а затем перетащите текстовое поле внутрь верхнего колонтитула отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-263">On the **Insert** tab, click **Text Box**, and then drag a text box inside the report header.</span></span> <span data-ttu-id="30ac0-264">Установите длину текстового поля около 6 дюймов, а высоту 3/4 дюйма и поместите его в левой части верхнего колонтитула отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-264">Make the text box about 6 inches long and 3/4 inch tall and place it on the left side of the report header.</span></span>  
  
5.  <span data-ttu-id="30ac0-265">В текстовом поле введите **Продажи по территориям, подкатегориям и дням**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-265">In the text box, type **Sales by Territory, Subcategory, and Day**.</span></span>  
  
6.  <span data-ttu-id="30ac0-266">Выделите введенный текст, щелкните его правой кнопкой мыши и выберите пункт **Свойства текста**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-266">Select the text you typed, right-click, and then click **Text Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30ac0-267">Чтобы можно было отформатировать символы одновременно, они должны быть смежными.</span><span class="sxs-lookup"><span data-stu-id="30ac0-267">To format characters at the same time, they must be contiguous.</span></span>  
  
7.  <span data-ttu-id="30ac0-268">В диалоговом окне **Свойства текста** нажмите кнопку **Шрифт**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-268">In the **Text Properties** dialog box, click **Font**.</span></span>  
  
8.  <span data-ttu-id="30ac0-269">В списке **Шрифт** выберите **Times New Roman**; в списке **Размер** выберите **24 пт**, в списке **Цвет** выберите **каштановый**, а в списке **стиль** выберите **курсив**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-269">In the **Font** list, select **Times New Roman**; in **Size** select **24 pt**, in **Color** select **Maroon**, and in **Style** select **Italic**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="30ac0-270">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-270">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="30ac0-271">Отчет включает заголовок отчета в верхнем колонтитуле отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-271">The report includes a report title in the report header.</span></span>  
  
##  <a name="8-save-the-report"></a><a name="Save"></a><span data-ttu-id="30ac0-272">8. Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="30ac0-272">8. Save the Report</span></span>  
 <span data-ttu-id="30ac0-273">Отчеты можно сохранять на сервере отчетов, в библиотеке SharePoint или на компьютере.</span><span class="sxs-lookup"><span data-stu-id="30ac0-273">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="30ac0-274">В данном учебнике предусмотрено сохранение отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-274">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="30ac0-275">Если нет доступа к серверу отчетов, сохраните отчет на компьютере.</span><span class="sxs-lookup"><span data-stu-id="30ac0-275">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="30ac0-276">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="30ac0-276">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="30ac0-277">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-277">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="30ac0-278">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-278">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="30ac0-279">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-279">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="30ac0-280">Появится сообщение «Соединение с сервером отчетов».</span><span class="sxs-lookup"><span data-stu-id="30ac0-280">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="30ac0-281">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов в качестве места хранения отчетов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="30ac0-281">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="30ac0-282">В поле **Имя**замените имя по умолчанию на **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-282">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
5.  <span data-ttu-id="30ac0-283">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-283">Click **Save**.</span></span>  
  
 <span data-ttu-id="30ac0-284">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="30ac0-284">The report is saved to the report server.</span></span> <span data-ttu-id="30ac0-285">Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="30ac0-285">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="30ac0-286">Сохранение отчета на компьютере</span><span class="sxs-lookup"><span data-stu-id="30ac0-286">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="30ac0-287">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-287">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="30ac0-288">Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="30ac0-288">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="30ac0-289">В поле **Имя**замените имя по умолчанию на **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-289">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
4.  <span data-ttu-id="30ac0-290">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-290">Click **Save**.</span></span>  
  
##  <a name="9-optional-rotate-text-box-270-degrees"></a><a name="RotateTextBox"></a><span data-ttu-id="30ac0-291">9. поворот текстового поля на 270 градусов (необязательно)</span><span class="sxs-lookup"><span data-stu-id="30ac0-291">9. (Optional) Rotate Text Box 270 Degrees</span></span>  
 <span data-ttu-id="30ac0-292">Отчет, содержащий матрицы, при выполнении обычно может расширяться как по горизонтали, так и по вертикали.</span><span class="sxs-lookup"><span data-stu-id="30ac0-292">A report with matrices can expand horizontally and vertically when it runs.</span></span> <span data-ttu-id="30ac0-293">Поворачивая текстовые поля по вертикали, или на 270 градусов, можно сэкономить пространство в горизонтальном направлении.</span><span class="sxs-lookup"><span data-stu-id="30ac0-293">By rotating text boxes vertically, or 270 degrees, you can save horizontal space.</span></span> <span data-ttu-id="30ac0-294">В этом случае ширина подготовленного к просмотру отчета уменьшается и при экспорте в такой формат, как Microsoft Word, удобнее помещается на печатной странице.</span><span class="sxs-lookup"><span data-stu-id="30ac0-294">The rendered report is then narrower and if exported to a format such as Microsoft Word, will be more likely to fit on a printed page.</span></span>  
  
 <span data-ttu-id="30ac0-295">Кроме того, в текстовом поле можно отображать текст как горизонтальный или вертикальный (сверху вниз).</span><span class="sxs-lookup"><span data-stu-id="30ac0-295">A text box can also display text as horizontal, vertical (top to bottom).</span></span> <span data-ttu-id="30ac0-296">Дополнительные сведения см. в разделе [Текстовые поля (построитель отчетов и службы SSRS)](report-design/text-boxes-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="30ac0-296">For more information, see [Text Boxes &#40;Report Builder and SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-rotate-text-box-270-degrees"></a><span data-ttu-id="30ac0-297">Поворот текстового поля на 270 градусов</span><span class="sxs-lookup"><span data-stu-id="30ac0-297">To rotate text box 270 degrees</span></span>  
  
1.  <span data-ttu-id="30ac0-298">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="30ac0-298">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="30ac0-299">Щелкните ячейку, содержащую `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="30ac0-299">Click the cell that contains `[Territory].`</span></span>  
  
3.  <span data-ttu-id="30ac0-300">В области Свойства перейдите к свойству WritingMode и в раскрывающемся списке выберите **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-300">In the Properties pane, locate the WritingMode property and in its drop-down list, select **Rotate270**.</span></span>  
  
     <span data-ttu-id="30ac0-301">Если панель свойств не открыта, перейдите на вкладку **Вид** ленты и установите флажок **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="30ac0-301">If the Properties pane is not open, click the **View** tab of the ribbon, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="30ac0-302">Убедитесь, что для свойства CanGrow задано значение `True` .</span><span class="sxs-lookup"><span data-stu-id="30ac0-302">Verify that the CanGrow property is set to `True`.</span></span>  
  
5.  <span data-ttu-id="30ac0-303">Измените размер столбца Territory, установив ширину 1/2 дюйма, и удалите заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="30ac0-303">Resize the Territory column to be 1/2 inch wide and delete the column title.</span></span>  
  
6.  <span data-ttu-id="30ac0-304">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="30ac0-304">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="30ac0-305">Название территории написано по вертикали, снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="30ac0-305">The territory name is written vertically, bottom to top.</span></span> <span data-ttu-id="30ac0-306">Высота группы строк Territory изменяется в зависимости от длины названия территории.</span><span class="sxs-lookup"><span data-stu-id="30ac0-306">The height of the Territory row group varies by the length of the territory name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="30ac0-307">Next Steps</span><span class="sxs-lookup"><span data-stu-id="30ac0-307">Next Steps</span></span>  
 <span data-ttu-id="30ac0-308">На этом работа с учебником по созданию матричного отчета закончена.</span><span class="sxs-lookup"><span data-stu-id="30ac0-308">This concludes the tutorial for how to create a matrix report.</span></span> <span data-ttu-id="30ac0-309">Дополнительные сведения о матрицах см. в разделах [таблицы, матрицы и списки &#40;построитель отчетов и службы ssrs&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [матрицы &#40;построитель отчетов и SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [области данных табликса &#40;построитель отчетов и SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)и [ячейки, строки и столбцы области данных табликса &#40;построитель отчетов&#41; и SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="30ac0-309">For more information about matrices, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Matrices &#40;Report Builder and SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ac0-310">См. также:</span><span class="sxs-lookup"><span data-stu-id="30ac0-310">See Also</span></span>  
 <span data-ttu-id="30ac0-311">[Учебники &#40;построитель отчетов&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="30ac0-311">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="30ac0-312">Построитель отчетов в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="30ac0-312">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
