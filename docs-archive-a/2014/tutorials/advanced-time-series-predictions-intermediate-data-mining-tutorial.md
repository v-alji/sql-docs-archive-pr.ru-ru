---
title: Расширенные прогнозы временных рядов (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b614ebdb-07ca-44af-a0ff-893364bd4b71
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 70ebf856ba0782cbf44969aba30602818015582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735669"
---
# <a name="advanced-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="aaccb-102">Расширенные прогнозы временных рядов (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="aaccb-102">Advanced Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="aaccb-103">В ходе изучения модели прогнозирования было показано, что хотя продажи в большинстве регионов и следуют схожему шаблону, некоторые регионы и некоторые модели, например модель M200 в Тихоокеанском регионе, имеют очень разные тренды.</span><span class="sxs-lookup"><span data-stu-id="aaccb-103">You saw from exploring the forecasting model that although sales in most of the regions follow a similar pattern, some regions and some models, such as the M200 model in the Pacific region, exhibit very different trends.</span></span> <span data-ttu-id="aaccb-104">Это не удивляет, поскольку различия между регионами не являются редкостью и могут быть вызваны многими факторами, включая маркетинговые акции, неточные отчеты или геополитические события.</span><span class="sxs-lookup"><span data-stu-id="aaccb-104">This does not surprise you, as you know that differences among regions are common and can be caused by many factors, including marketing promotions, inaccurate reporting, or geopolitical events.</span></span>  
  
 <span data-ttu-id="aaccb-105">Тем не менее, пользователям нужна модель, применимая к любым странам мира.</span><span class="sxs-lookup"><span data-stu-id="aaccb-105">However, your users are asking for a model that can be applied worldwide.</span></span> <span data-ttu-id="aaccb-106">Поэтому чтобы максимально снизить воздействие индивидуальных факторов на проекции, принимается решение создать модель, основанную на агрегатных вычислениях продаж по всему миру.</span><span class="sxs-lookup"><span data-stu-id="aaccb-106">Therefore, to minimize the effect of individual factors on projections, you decide to build a model that is based on aggregated measures of worldwide sales.</span></span> <span data-ttu-id="aaccb-107">Эту модель затем можно использовать для прогнозирования по каждому отдельному региону.</span><span class="sxs-lookup"><span data-stu-id="aaccb-107">You can then use this model to make predictions for each individual region.</span></span>  
  
 <span data-ttu-id="aaccb-108">В этой задаче будут построены все источники данных, необходимые для выполнения расширенных задач прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="aaccb-108">In this task, you will build all the data sources that you need to perform the advanced prediction tasks.</span></span> <span data-ttu-id="aaccb-109">Будут созданы два представления источников данных, которые будут использоваться в качестве входных данных прогнозирующего запроса, и одно представление источника данных для построения новой модели.</span><span class="sxs-lookup"><span data-stu-id="aaccb-109">You will create two data source views for use as inputs to the prediction query, and one data source view to use in building a new model.</span></span>  
  
 <span data-ttu-id="aaccb-110">**Шаги**</span><span class="sxs-lookup"><span data-stu-id="aaccb-110">**Steps**</span></span>  
  
1.  [<span data-ttu-id="aaccb-111">Подготовка расширенных данных по продажам (для прогноза)</span><span class="sxs-lookup"><span data-stu-id="aaccb-111">Prepare the extended sales data (for prediction)</span></span>](#bkmk_newExtendData)  
  
2.  [<span data-ttu-id="aaccb-112">Подготовка статистических данных (для построения модели)</span><span class="sxs-lookup"><span data-stu-id="aaccb-112">Prepare the aggregated data (for building the model)</span></span>](#bkmk_newReplaceData)  
  
3.  [<span data-ttu-id="aaccb-113">Подготовка данных рядов (для перекрестного прогнозирования)</span><span class="sxs-lookup"><span data-stu-id="aaccb-113">Prepare the series data (for cross-prediction)</span></span>](#bkmk_CrossData2)  
  
4.  [<span data-ttu-id="aaccb-114">Прогноз с помощью EXTEND</span><span class="sxs-lookup"><span data-stu-id="aaccb-114">Predict using EXTEND</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
5.  [<span data-ttu-id="aaccb-115">Создание модели перекрестного прогнозирования</span><span class="sxs-lookup"><span data-stu-id="aaccb-115">Create the cross-prediction model</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
6.  [<span data-ttu-id="aaccb-116">Прогноз с помощью REPLACE</span><span class="sxs-lookup"><span data-stu-id="aaccb-116">Predict using REPLACE</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
7.  [<span data-ttu-id="aaccb-117">Просмотр новых результатов прогноза</span><span class="sxs-lookup"><span data-stu-id="aaccb-117">Review the new predictions</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
##  <a name="creating-the-new-extended-sales-data"></a><a name="bkmk_newExtendData"></a><span data-ttu-id="aaccb-118">Создание новых данных расширенных продаж</span><span class="sxs-lookup"><span data-stu-id="aaccb-118">Creating the New Extended Sales Data</span></span>  
 <span data-ttu-id="aaccb-119">Для обновления данных о продажах нужно будет получить последние цифры продаж.</span><span class="sxs-lookup"><span data-stu-id="aaccb-119">To update your sales data, you will need to get the latest sales figures.</span></span> <span data-ttu-id="aaccb-120">Особенно важными являются данные из Тихоокеанского региона, где была запущена региональная акция продаж для привлечения внимания к новым магазинам и информирования о продукции.</span><span class="sxs-lookup"><span data-stu-id="aaccb-120">Of particular interest are the data just in from the Pacific region, which launched a regional sales promotion to call attention to the new stores and raise awareness of their products.</span></span>  
  
 <span data-ttu-id="aaccb-121">В этом сценарии предполагается, что данные были импортированы из книги Excel, содержащей всего три месяца новых данных для нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="aaccb-121">For this scenario, we'll assume that the data has been imported from an Excel workbook that contains just three months of new data for a couple of regions.</span></span> <span data-ttu-id="aaccb-122">Вы создадите таблицу для данных с помощью скрипта Transact-SQL, а затем определите представление источника данных, которое будет использоваться для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="aaccb-122">You'll create a table for the data using a Transact-SQL script, and then define a data source view to use for prediction.</span></span>  
  
#### <a name="create-the-table-with-new-sales-data"></a><span data-ttu-id="aaccb-123">Создание таблицы с новыми данными о продажах</span><span class="sxs-lookup"><span data-stu-id="aaccb-123">Create the table with new sales data</span></span>  
  
1.  <span data-ttu-id="aaccb-124">В окне запросов Transact-SQL выполните следующую инструкцию, чтобы добавить данные о продажах в базу данных AdventureWorksDW (или в любую другую базу данных).</span><span class="sxs-lookup"><span data-stu-id="aaccb-124">In a Transact-SQL query window, execute the following statement to add the sales data to the AdventureWorksDW database (or any other database).</span></span>  
  
    ```  
    USE [database name];  
    GO  
    IF OBJECT_ID ([dbo].[NewSalesData]) IS NOT NULL   
        DROP TABLE [dbo].[NewSalesData];  
    GO  
    CREATE TABLE [dbo].[NewSalesData]([Series] [nvarchar](255) NULL,  
    [NewDate] [datetime] NULL,  
    [NewQty] [float] NULL,  
    [NewAmount] [money] NULL) ON [PRIMARY]  
  
    GO  
    ```  
  
2.  <span data-ttu-id="aaccb-125">Вставьте новые значения с помощью следующего скрипта.</span><span class="sxs-lookup"><span data-stu-id="aaccb-125">Insert the new values using the following script.</span></span>  
  
    ```  
    INSERT INTO [NewSalesData]  
    (Series,NewDate,NewQty,NewAmount)  
    VALUES('T1000 Pacific', '7/25/08', 55, '$130,170.22'),  
    ('T1000 Pacific', '8/25/08', 50, '$114,435.36 '),  
    ('T1000 Pacific', '9/25/08', 50, '$117,296.24 '),  
    ('T1000 Europe', '7/25/08', 37, '$88,210.00 '),  
    ('T1000 Europe', '8/25/08', 41, '$97,746.00 '),  
    ('T1000 Europe', '9/25/08', 37, '$88,210.00 '),  
    ('T1000 North America', '7/25/08', 69, '$164,500.00 '),  
    ('T1000 North America', '8/25/08', 66, '$157,348.00 '),  
    ('T1000 North America', '9/25/08', 58, '$138,276.00 '),  
    ('M200 Pacific', '7/25/08', 65, '$149,824.35'),  
    ('M200 Pacific', '8/25/08', 54,  '$124,619.46'),  
    ('M200 Pacific', '9/25/08', 61, '$141,143.39'),  
    ('M200 Europe', '7/25/08', 75, '$173,026.00'),  
    ('M200 Europe', '8/25/08', 76, '$175,212.00'),  
    ('M200 Europe', '9/25/08', 84, '$193,731.00'),  
    ('M200 North America', '7/25/08', 94, '$216,916.00'),  
    ('M200 North America', '8/25/08', 94, '$216,891.00'),  
    ('M200 North America', '9/25/08', 91,'$209,943.00');  
    ```  
  
    > [!WARNING]  
    >  <span data-ttu-id="aaccb-126">Кавычки используются для значений валют, чтобы не возникало проблем с разделителем в виде запятой и символом валюты.</span><span class="sxs-lookup"><span data-stu-id="aaccb-126">The quotation marks are used with the currency values to prevent problems with the comma separator and the currency symbol.</span></span> <span data-ttu-id="aaccb-127">Значения валют можно также передавать в следующем формате: `130170.22`</span><span class="sxs-lookup"><span data-stu-id="aaccb-127">You could also pass in the currency values in this format: `130170.22`</span></span>  
    >   
    >  <span data-ttu-id="aaccb-128">Обратите внимание, что даты, используемые в образце базы данных, изменены для этой версии.</span><span class="sxs-lookup"><span data-stu-id="aaccb-128">Note that the dates used in the sample database have changed for this release.</span></span> <span data-ttu-id="aaccb-129">Если используется более раннее издание AdventureWorks, вставленные даты, возможно, потребуется соответствующим образом скорректировать.</span><span class="sxs-lookup"><span data-stu-id="aaccb-129">If you are using an earlier edition of AdventureWorks, you might need to adjust the inserted dates accordingly.</span></span>  
  
###  <a name="create-a-data-source-view-using-the-new-sales-data"></a><a name="bkmk_newReplaceData"></a><span data-ttu-id="aaccb-130">Создание представления источника данных с помощью новых данных о продажах</span><span class="sxs-lookup"><span data-stu-id="aaccb-130">Create a data source view using the new sales data</span></span>  
  
1.  <span data-ttu-id="aaccb-131">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **представления источников данных**и выберите пункт **создать представление источника данных**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-131">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="aaccb-132">В окне мастера представлений источников данных выберите указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="aaccb-132">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="aaccb-133">**Источник данных**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaccb-133">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="aaccb-134">**Выбор таблиц и представлений**: выберите только что созданную таблицу, невсалесдата.</span><span class="sxs-lookup"><span data-stu-id="aaccb-134">**Select Tables and Views**: Select the table that you just created, NewSalesData.</span></span>  
  
3.  <span data-ttu-id="aaccb-135">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-135">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="aaccb-136">В области конструктора представления источников данных щелкните правой кнопкой мыши Невсалесдата и выберите **Просмотр данных** , чтобы проверить данные.</span><span class="sxs-lookup"><span data-stu-id="aaccb-136">In the Data Source View design surface, right-click NewSalesData, and then select **Explore Data** to verify the data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="aaccb-137">Эти данные будут использоваться только для прогноза, поэтому если они неполные, это не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="aaccb-137">You will use this data for prediction only, so it does not matter that the data is incomplete.</span></span>  
  
##  <a name="creating-the-data-for-the-cross-prediction-model"></a><a name="bkmk_CrossData2"></a><span data-ttu-id="aaccb-138">Создание данных для модели перекрестного прогнозирования</span><span class="sxs-lookup"><span data-stu-id="aaccb-138">Creating the Data for the Cross-Prediction Model</span></span>  
 <span data-ttu-id="aaccb-139">Данные, использованные в исходной модели прогнозирования, уже были сгруппированы с помощью представления vTimeSeries, которое разбивает несколько моделей велосипедов на более мелкие категории и сводит результаты из отдельных стран в регионы.</span><span class="sxs-lookup"><span data-stu-id="aaccb-139">The data that was used in the original forecasting model was already grouped somewhat by the view vTimeSeries, which collapsed several bike models into a smaller number of categories, and merged results from individual countries into regions.</span></span> <span data-ttu-id="aaccb-140">Чтобы создать модель для проекций для стран всего мира, потребуется создать некоторые простые агрегатные функции напрямую в конструкторе представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="aaccb-140">To create a model that can be used for world-wide projections, you will create some additional simple aggregations directly in the Data Source View Designer.</span></span> <span data-ttu-id="aaccb-141">Новое представление источника данных будет содержать только сумму и среднее значение продаж всех продуктов для всех регионов.</span><span class="sxs-lookup"><span data-stu-id="aaccb-141">The new data source view will contain just a sum and an average of the sales of all products for all regions.</span></span>  
  
 <span data-ttu-id="aaccb-142">После создания источника данных для модели следует создать новое представление источников данных для прогноза.</span><span class="sxs-lookup"><span data-stu-id="aaccb-142">After you have created the data source used for the model, you must create a new data source view to use for prediction.</span></span> <span data-ttu-id="aaccb-143">Например, если нужно спрогнозировать продажи для Европы с помощью новой мировой модели, нужно передать данные только для Европы.</span><span class="sxs-lookup"><span data-stu-id="aaccb-143">For example, if you want to predict sales for Europe using the new worldwide model, you must feed in data for the Europe region only.</span></span> <span data-ttu-id="aaccb-144">Таким образом будет настроено новое представление источников данных, которое будет фильтровать исходные данные и изменит условие фильтра для каждого набора прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="aaccb-144">So you will set up a new data source view that filters the original data, and change the filter condition for each set of prediction queries.</span></span>  
  
#### <a name="to-create-the-model-data-using-a-custom-data-source-view"></a><span data-ttu-id="aaccb-145">Создание данных модели с помощью пользовательского представления источников данных</span><span class="sxs-lookup"><span data-stu-id="aaccb-145">To create the model data using a custom data source view</span></span>  
  
1.  <span data-ttu-id="aaccb-146">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **представления источников данных**и выберите пункт **создать представление источника данных**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-146">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="aaccb-147">На странице приветствия мастера нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-147">On the welcome page of the wizard, click **Next**.</span></span>  
  
3.  <span data-ttu-id="aaccb-148">На странице **Выбор источника данных** выберите [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-148">On the **Select Data Source** page, select [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="aaccb-149">На странице **выберите таблицы и представления**, не добавляйте таблицы — просто нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-149">In the page, **Select Tables and Views**, do not add any tables-just click **Next**.</span></span>  
  
5.  <span data-ttu-id="aaccb-150">На странице **Завершение работы мастера**введите имя `AllRegions` и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-150">On the page, **Completing the Wizard**, type the name `AllRegions`, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="aaccb-151">Затем щелкните правой кнопкой мыши пустую область конструктора представления источника данных и выберите **создать именованный запрос**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-151">Next, right-click the blank data source view design surface, and then select **New Named Query**.</span></span>  
  
7.  <span data-ttu-id="aaccb-152">В диалоговом окне **Создание именованного запроса** в поле **имя**, тип `AllRegions` и **Описание**введите **Sum и Average для продаж по всем моделям и регионам**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-152">In the **Create Named Query** dialog box, for **Name**, type `AllRegions`, and for **Description**, type **Sum and average of sales for all models and regions**.</span></span>  
  
8.  <span data-ttu-id="aaccb-153">В панели SQL-текста введи следующую инструкцию и нажмите кнопку «ОК»:</span><span class="sxs-lookup"><span data-stu-id="aaccb-153">In the SQL text pane, type the following statement and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate,   
    SUM([Quantity]) as SumQty, AVG([Quantity]) as AvgQty,  
    SUM([Amount]) AS SumAmt, AVG([Amount]) AS AvgAmt,  
    'All Regions' as [Region]  
    FROM dbo.vTimeSeries   
    GROUP BY ReportingDate  
    ```  
  
9. <span data-ttu-id="aaccb-154">Щелкните правой кнопкой мыши `AllRegions` таблицу и выберите **Просмотр данных**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-154">Right-click the `AllRegions` table, and then select **Explore Data**.</span></span>  
  
###  <a name="to-create-the-series-data-for-cross-prediction"></a><a name="bkmk_CrossData"></a><span data-ttu-id="aaccb-155">Создание данных ряда для перекрестного прогнозирования</span><span class="sxs-lookup"><span data-stu-id="aaccb-155">To create the series data for cross-prediction</span></span>  
  
1.  <span data-ttu-id="aaccb-156">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **представления источников данных**и выберите пункт **создать представление источника данных**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-156">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="aaccb-157">В окне мастера представлений источников данных выберите указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="aaccb-157">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="aaccb-158">**Источник данных**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaccb-158">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="aaccb-159">**Выбор таблиц и представлений**: не выбирайте никаких таблиц.</span><span class="sxs-lookup"><span data-stu-id="aaccb-159">**Select Tables and Views**: Do not select any tables</span></span>  
  
     <span data-ttu-id="aaccb-160">**Имя**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="aaccb-160">**Name**: `T1000 Pacific Region`</span></span>  
  
3.  <span data-ttu-id="aaccb-161">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-161">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="aaccb-162">Щелкните правой кнопкой мыши пустую область конструктора для **T1000 Тихоокеанского региона. dsv**и выберите **создать именованный запрос**.</span><span class="sxs-lookup"><span data-stu-id="aaccb-162">Right-click the empty design surface for **T1000 Pacific Region.dsv**, and then select **New Named Query**.</span></span>  
  
     <span data-ttu-id="aaccb-163">Откроется диалоговое окно **Создание именованного запроса** .</span><span class="sxs-lookup"><span data-stu-id="aaccb-163">The **Create Named Query** dialog box appears.</span></span> <span data-ttu-id="aaccb-164">Снова введите имя и добавьте следующее описание:</span><span class="sxs-lookup"><span data-stu-id="aaccb-164">Retype the name, and then add the following description:</span></span>  
  
     <span data-ttu-id="aaccb-165">**Имя**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="aaccb-165">**Name**: `T1000 Pacific Region`</span></span>  
  
     <span data-ttu-id="aaccb-166">**Описание**: **Фильтрация `vTimeSeries` по регионам и моделям**</span><span class="sxs-lookup"><span data-stu-id="aaccb-166">**Description**: **Filter`vTimeSeries`by region and model**</span></span>  
  
5.  <span data-ttu-id="aaccb-167">В панели ввода текста введите следующий запрос и нажмите кнопку ОК:</span><span class="sxs-lookup"><span data-stu-id="aaccb-167">In the text pane, type the following query, and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate, ModelRegion, Quantity, Amount  
    FROM dbo.vTimeSeries  
    WHERE (ModelRegion = N'T1000 Pacific')  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="aaccb-168">Поскольку для каждого ряда нужно создавать свой прогноз, текст запроса можно скопировать и сохранить в текстовый файл, чтобы использовать его повторно для других рядов данных.</span><span class="sxs-lookup"><span data-stu-id="aaccb-168">Since you will need to create predictions for each series separately, you might want to copy the query text and save it to a text file so that you can re-use it for the other data series.</span></span>  
  
6.  <span data-ttu-id="aaccb-169">В области конструктора представления источников данных щелкните правой кнопкой мыши T1000 Тихоокеанский регион и выберите **Просмотр данных** , чтобы убедиться, что данные отфильтрованы правильно.</span><span class="sxs-lookup"><span data-stu-id="aaccb-169">In the Data Source View design surface, right-click T1000 Pacific, and then select **Explore Data** to verify that the data is filtered correctly.</span></span>  
  
     <span data-ttu-id="aaccb-170">Эти данные будут использоваться как входные данные для модели при запросах перекрестного прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="aaccb-170">You will use this data as the input to the model when creating cross-prediction queries.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="aaccb-171">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="aaccb-171">Next Task in Lesson</span></span>  
 [<span data-ttu-id="aaccb-172">Прогнозирование временных рядов с помощью обновленного учебника по интеллектуальному анализу данных &#40;данных&#41;</span><span class="sxs-lookup"><span data-stu-id="aaccb-172">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="aaccb-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="aaccb-173">See Also</span></span>  
 <span data-ttu-id="aaccb-174">[Алгоритм временных рядов (Майкрософт)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="aaccb-174">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 <span data-ttu-id="aaccb-175">[Технический справочник по алгоритму временных рядов (Майкрософт)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="aaccb-175">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="aaccb-176">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="aaccb-176">Data Source Views in Multidimensional Models</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models)  
  
  
