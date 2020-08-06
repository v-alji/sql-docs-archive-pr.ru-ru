---
title: Занятие 5. расширение модели временных рядов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7aad4946-c903-4e25-88b9-b087c20cb67d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2716e985897f8115d189d9410b7cdb13fb1af291
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657432"
---
# <a name="lesson-5-extending-the-time-series-model"></a><span data-ttu-id="d8493-102">Занятие 5.: Расширение модели временных рядов</span><span class="sxs-lookup"><span data-stu-id="d8493-102">Lesson 5: Extending the Time Series Model</span></span>
  <span data-ttu-id="d8493-103">В выпуске [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise в модель временных рядов можно добавлять новые данные и автоматически встраивать в эту модель новые данные.</span><span class="sxs-lookup"><span data-stu-id="d8493-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, you can add new data to a time series model and automatically incorporate the new data into the model.</span></span> <span data-ttu-id="d8493-104">Добавить новые данные в модель интеллектуального анализа данных временных рядов можно одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="d8493-104">You add new data to a time series mining model in one of two ways:</span></span>  
  
-   <span data-ttu-id="d8493-105">Использовать PREDICTION JOIN для соединения данных из внешнего источника с обучающими данными.</span><span class="sxs-lookup"><span data-stu-id="d8493-105">Use a PREDICTION JOIN to join data in an external source to the training data.</span></span>  
  
-   <span data-ttu-id="d8493-106">Использовать одноэлементный прогнозирующий запрос для предоставления каждый раз данных только одного среза.</span><span class="sxs-lookup"><span data-stu-id="d8493-106">Use a singleton prediction query to provide data one slice at a time.</span></span>  
  
 <span data-ttu-id="d8493-107">Предположим, что несколько месяцев назад проводилось обучение модели интеллектуального анализа данных на существующих данных продаж.</span><span class="sxs-lookup"><span data-stu-id="d8493-107">For example, assume that you trained the mining model on existing sales data some months ago.</span></span> <span data-ttu-id="d8493-108">При выполнении новых продаж может понадобиться обновить прогнозы продаж, чтобы учесть новые данные.</span><span class="sxs-lookup"><span data-stu-id="d8493-108">When you get new sales, you might want to update the sales predictions to incorporate the new data.</span></span> <span data-ttu-id="d8493-109">Это можно сделать за один шаг, предоставив новые показатели продаж в качестве входных данных и формируя новые прогнозы на базе основного набора данных.</span><span class="sxs-lookup"><span data-stu-id="d8493-109">You can do this in one step, by supplying the new sales figures as input data and generating new predictions based on the composite data set.</span></span>  
  
## <a name="making-predictions-with-extend_model_cases"></a><span data-ttu-id="d8493-110">Прогнозирование с помощью EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d8493-110">Making Predictions with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="d8493-111">Далее представлены универсальные примеры прогноза временного ряда с использованием параметра EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="d8493-111">The following are generic examples of a time series prediction using EXTEND_MODEL_CASES.</span></span> <span data-ttu-id="d8493-112">Первый пример позволяет задать число прогнозов, начиная с последнего временного шага исходной модели.</span><span class="sxs-lookup"><span data-stu-id="d8493-112">The first example enables you to specify the number of predictions starting from the last time step of the original model:</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>]  
```  
  
 <span data-ttu-id="d8493-113">Второй пример позволяет задать временной шаг, где должно быть начато прогнозирование и где оно должно быть закончено.</span><span class="sxs-lookup"><span data-stu-id="d8493-113">The second example enables you to specify the time step where predictions should start, and where they should end.</span></span> <span data-ttu-id="d8493-114">Эта возможность важна при расширении вариантов модели, поскольку по умолчанию временные шаги, используемые для прогнозирующих запросов, всегда начинаются в конце исходного ряда.</span><span class="sxs-lookup"><span data-stu-id="d8493-114">This option is important when you extend the model cases because, by default, the time steps used for prediction queries always start at the end of the original series.</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n-start, n-end, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>}  
```  
  
 <span data-ttu-id="d8493-115">В этом учебнике будут созданы оба типа запросов.</span><span class="sxs-lookup"><span data-stu-id="d8493-115">In this tutorial, you will create both kinds of queries.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query-on-a-time-series-model"></a><span data-ttu-id="d8493-116">Создание одноэлементного прогнозирующего запроса на модели временных рядов</span><span class="sxs-lookup"><span data-stu-id="d8493-116">To create a singleton prediction query on a time series model</span></span>  
  
1.  <span data-ttu-id="d8493-117">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="d8493-117">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="d8493-118">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="d8493-118">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="d8493-119">Скопируйте общий пример одноэлементной инструкции в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="d8493-119">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="d8493-120">Вместо</span><span class="sxs-lookup"><span data-stu-id="d8493-120">Replace the following:</span></span>  
  
    ```  
    SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
    ```  
  
     <span data-ttu-id="d8493-121">на:</span><span class="sxs-lookup"><span data-stu-id="d8493-121">with:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    ```  
  
     <span data-ttu-id="d8493-122">В первой строке извлекается значение из модели, которая идентифицирует ряд.</span><span class="sxs-lookup"><span data-stu-id="d8493-122">The first line retrieves a value from the model that identifies the series.</span></span>  
  
     <span data-ttu-id="d8493-123">Следующая строка содержит прогнозирующую функцию, которая получает 6 прогнозов для Quantity.</span><span class="sxs-lookup"><span data-stu-id="d8493-123">The second line contains the prediction function, which gets 6 predictions for Quantity.</span></span> <span data-ttu-id="d8493-124">Псевдоним `PredictQty` присваивается столбцу результата прогноза, чтобы облегчить понимание результатов.</span><span class="sxs-lookup"><span data-stu-id="d8493-124">An alias, `PredictQty`, is assigned to the prediction result column to make it easier to understand the results.</span></span>  
  
4.  <span data-ttu-id="d8493-125">Вместо</span><span class="sxs-lookup"><span data-stu-id="d8493-125">Replace the following:</span></span>  
  
    ```  
    FROM <mining model>  
    ```  
  
     <span data-ttu-id="d8493-126">на:</span><span class="sxs-lookup"><span data-stu-id="d8493-126">with:</span></span>  
  
    ```  
    FROM [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="d8493-127">Вместо</span><span class="sxs-lookup"><span data-stu-id="d8493-127">Replace the following:</span></span>  
  
    ```  
    PREDICTION JOIN <source query>  
    ```  
  
     <span data-ttu-id="d8493-128">на:</span><span class="sxs-lookup"><span data-stu-id="d8493-128">with:</span></span>  
  
    ```  
    NATURAL PREDICTION JOIN   
    (  
       SELECT 1 AS [Reporting Date],  
       '10' AS [Quantity],  
       'M200 Europe' AS [Model Region]  
       UNION SELECT  
       2 AS [Reporting Date],  
       15 AS [Quantity]),  
       'M200 Europe' AS [Model Region]  
    ) AS t  
    ```  
  
6.  <span data-ttu-id="d8493-129">Вместо</span><span class="sxs-lookup"><span data-stu-id="d8493-129">Replace the following:</span></span>  
  
    ```  
    [WHERE <criteria>]  
    ```  
  
     <span data-ttu-id="d8493-130">на:</span><span class="sxs-lookup"><span data-stu-id="d8493-130">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="d8493-131">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d8493-131">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    FROM  
       [Forecasting_MIXED]  
    NATURAL PREDICTION JOIN   
       SELECT 1 AS [ReportingDate],  
      '10' AS [Quantity],  
      'M200 Europe' AS [ModelRegion]  
    UNION SELECT  
      2 AS [ReportingDate],  
      15 AS [Quantity]),  
      'M200 Europe' AS [ModelRegion]  
    ) AS t  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
7.  <span data-ttu-id="d8493-132">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="d8493-132">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="d8493-133">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Singleton_TimeSeries_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="d8493-133">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_TimeSeries_Query.dmx`.</span></span>  
  
9. <span data-ttu-id="d8493-134">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="d8493-134">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="d8493-135">Запрос возвращает прогнозы объема продаж велосипедов M200 в европейском и тихоокеанском регионах.</span><span class="sxs-lookup"><span data-stu-id="d8493-135">The query returns predictions of sales quantity for the M200 bicycle in the Europe and Pacific regions.</span></span>  
  
## <a name="understanding-prediction-start-with-extend_model_cases"></a><span data-ttu-id="d8493-136">Основные сведения о запуске прогноза при помощи параметра EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d8493-136">Understanding Prediction Start with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="d8493-137">Теперь, после создания прогнозов, основанных на исходной модели, и имея новые данные, можно сравнить результаты, чтобы увидеть, каким образом обновление данных продаж влияет на прогнозы.</span><span class="sxs-lookup"><span data-stu-id="d8493-137">Now that you have created predictions based on the original model, and with new data, you can compare the results to see how updating the sales data affects the predictions.</span></span> <span data-ttu-id="d8493-138">Перед этим просмотрите только что созданный код и обратите внимание на следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="d8493-138">Before you do so, review the code that you just created, and notice the following:</span></span>  
  
-   <span data-ttu-id="d8493-139">Предоставлены новые данные только для европейского региона.</span><span class="sxs-lookup"><span data-stu-id="d8493-139">You supplied new data for only the Europe region.</span></span>  
  
-   <span data-ttu-id="d8493-140">Предоставлены новые данные только за два месяца.</span><span class="sxs-lookup"><span data-stu-id="d8493-140">You supplied only two months' worth of new data.</span></span>  
  
 <span data-ttu-id="d8493-141">В следующей таблице показано, как новые значения, предоставленные для продаж модели M200 Europe, влияют на прогнозы.</span><span class="sxs-lookup"><span data-stu-id="d8493-141">The following table shows how the new values supplied for M200 Europe affect predictions.</span></span> <span data-ttu-id="d8493-142">Не предоставлены новые данные для продукта M200 в тихоокеанском регионе, но для сравнения представлен этот ряд.</span><span class="sxs-lookup"><span data-stu-id="d8493-142">You did not provide any new data for the M200 product in the Pacific region, but this series is presented for comparison:</span></span>  
  
 <span data-ttu-id="d8493-143">**Продукт и регион: M200 Европа**</span><span class="sxs-lookup"><span data-stu-id="d8493-143">**Product and Region: M200 Europe**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="d8493-144">Существующая модель (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="d8493-144">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="d8493-145">Модель с обновленными данными продаж (`PredictTimeSeries` с `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="d8493-145">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="d8493-146">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-146">M200 Europe</span></span>|<span data-ttu-id="d8493-147">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-147">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-148">77</span><span class="sxs-lookup"><span data-stu-id="d8493-148">77</span></span>|<span data-ttu-id="d8493-149">10</span><span class="sxs-lookup"><span data-stu-id="d8493-149">10</span></span>|  
|<span data-ttu-id="d8493-150">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-150">M200 Europe</span></span>|<span data-ttu-id="d8493-151">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-151">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-152">64</span><span class="sxs-lookup"><span data-stu-id="d8493-152">64</span></span>|<span data-ttu-id="d8493-153">15</span><span class="sxs-lookup"><span data-stu-id="d8493-153">15</span></span>|  
|<span data-ttu-id="d8493-154">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-154">M200 Europe</span></span>|<span data-ttu-id="d8493-155">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-155">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-156">59</span><span class="sxs-lookup"><span data-stu-id="d8493-156">59</span></span>|<span data-ttu-id="d8493-157">72</span><span class="sxs-lookup"><span data-stu-id="d8493-157">72</span></span>|  
|<span data-ttu-id="d8493-158">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-158">M200 Europe</span></span>|<span data-ttu-id="d8493-159">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-159">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-160">56</span><span class="sxs-lookup"><span data-stu-id="d8493-160">56</span></span>|<span data-ttu-id="d8493-161">69</span><span class="sxs-lookup"><span data-stu-id="d8493-161">69</span></span>|  
|<span data-ttu-id="d8493-162">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-162">M200 Europe</span></span>|<span data-ttu-id="d8493-163">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-163">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-164">56</span><span class="sxs-lookup"><span data-stu-id="d8493-164">56</span></span>|<span data-ttu-id="d8493-165">68</span><span class="sxs-lookup"><span data-stu-id="d8493-165">68</span></span>|  
|<span data-ttu-id="d8493-166">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-166">M200 Europe</span></span>|<span data-ttu-id="d8493-167">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-167">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-168">74</span><span class="sxs-lookup"><span data-stu-id="d8493-168">74</span></span>|<span data-ttu-id="d8493-169">89</span><span class="sxs-lookup"><span data-stu-id="d8493-169">89</span></span>|  
  
 <span data-ttu-id="d8493-170">**Продукт и регион: M200 по тихоокеанскому времени**</span><span class="sxs-lookup"><span data-stu-id="d8493-170">**Product and Region: M200 Pacific**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="d8493-171">Существующая модель (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="d8493-171">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="d8493-172">Модель с обновленными данными продаж (`PredictTimeSeries` с `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="d8493-172">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="d8493-173">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d8493-173">M200 Pacific</span></span>|<span data-ttu-id="d8493-174">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-174">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-175">41</span><span class="sxs-lookup"><span data-stu-id="d8493-175">41</span></span>|<span data-ttu-id="d8493-176">41</span><span class="sxs-lookup"><span data-stu-id="d8493-176">41</span></span>|  
|<span data-ttu-id="d8493-177">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d8493-177">M200 Pacific</span></span>|<span data-ttu-id="d8493-178">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-178">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-179">44</span><span class="sxs-lookup"><span data-stu-id="d8493-179">44</span></span>|<span data-ttu-id="d8493-180">44</span><span class="sxs-lookup"><span data-stu-id="d8493-180">44</span></span>|  
|<span data-ttu-id="d8493-181">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d8493-181">M200 Pacific</span></span>|<span data-ttu-id="d8493-182">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-182">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-183">38</span><span class="sxs-lookup"><span data-stu-id="d8493-183">38</span></span>|<span data-ttu-id="d8493-184">38</span><span class="sxs-lookup"><span data-stu-id="d8493-184">38</span></span>|  
|<span data-ttu-id="d8493-185">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d8493-185">M200 Pacific</span></span>|<span data-ttu-id="d8493-186">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-186">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-187">41</span><span class="sxs-lookup"><span data-stu-id="d8493-187">41</span></span>|<span data-ttu-id="d8493-188">41</span><span class="sxs-lookup"><span data-stu-id="d8493-188">41</span></span>|  
|<span data-ttu-id="d8493-189">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d8493-189">M200 Pacific</span></span>|<span data-ttu-id="d8493-190">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-190">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-191">36</span><span class="sxs-lookup"><span data-stu-id="d8493-191">36</span></span>|<span data-ttu-id="d8493-192">36</span><span class="sxs-lookup"><span data-stu-id="d8493-192">36</span></span>|  
|<span data-ttu-id="d8493-193">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d8493-193">M200 Pacific</span></span>|<span data-ttu-id="d8493-194">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-194">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-195">39</span><span class="sxs-lookup"><span data-stu-id="d8493-195">39</span></span>|<span data-ttu-id="d8493-196">39</span><span class="sxs-lookup"><span data-stu-id="d8493-196">39</span></span>|  
  
 <span data-ttu-id="d8493-197">Эти результаты позволяют сделать два вывода.</span><span class="sxs-lookup"><span data-stu-id="d8493-197">From these results, you can see two things:</span></span>  
  
-   <span data-ttu-id="d8493-198">Первые два прогноза для ряда M200 Europe точно совпадают с предоставленными новыми данными.</span><span class="sxs-lookup"><span data-stu-id="d8493-198">The first two predictions for the M200 Europe series are exactly the same as the new data you supplied.</span></span> <span data-ttu-id="d8493-199">Как определено при проектировании, службы Analysis Services возвращают новые точки данных вместо выполнения прогноза.</span><span class="sxs-lookup"><span data-stu-id="d8493-199">By design, Analysis Services returns the actual new data points instead of making a prediction.</span></span> <span data-ttu-id="d8493-200">Причина этого заключается в том, что при расширении вариантов модели временные шаги, используемые для прогнозирующих запросов, всегда начинаются в конце исходного ряда.</span><span class="sxs-lookup"><span data-stu-id="d8493-200">That is because when you extend the model cases, the time steps used for prediction queries always start at the end of the original series.</span></span> <span data-ttu-id="d8493-201">Следовательно, если добавляется две новые точки данных, первые два возвращенных прогноза перекрываются новыми данными.</span><span class="sxs-lookup"><span data-stu-id="d8493-201">Therefore, if you add two new data points, the first two predictions returned overlap with the new data.</span></span>  
  
-   <span data-ttu-id="d8493-202">После исчерпания новых точек данных службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] выполняют прогнозирование, основываясь обновленной модели.</span><span class="sxs-lookup"><span data-stu-id="d8493-202">After all the new data points are used up, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] makes predictions based on the updated model.</span></span> <span data-ttu-id="d8493-203">Поэтому начиная с сентября 2005 г. можно видеть разницу между прогнозами для M200 Europe для исходной модели, в левом столбце, и для модели, которая использует параметр EXTEND_MODEL_CASES, в правом столбце.</span><span class="sxs-lookup"><span data-stu-id="d8493-203">Therefore, starting in September 2005, you can see the difference between predictions for M200 Europe from the original model, in the left-hand column, and the model that uses EXTEND_MODEL_CASES, in the right-hand column.</span></span> <span data-ttu-id="d8493-204">Прогнозы будут отличаться, поскольку модель обновлена новыми данными.</span><span class="sxs-lookup"><span data-stu-id="d8493-204">The predictions are different because the model has been updated with the new data.</span></span>  
  
## <a name="using-start-and-end-time-steps-to-control-predictions"></a><span data-ttu-id="d8493-205">Использование начального и конечного временных шагов для управления прогнозированием</span><span class="sxs-lookup"><span data-stu-id="d8493-205">Using Start and End Time Steps to Control Predictions</span></span>  
 <span data-ttu-id="d8493-206">При расширении модели новые данные всегда присоединяются в конец ряда.</span><span class="sxs-lookup"><span data-stu-id="d8493-206">When you extend a model, the new data is always attached to the end of the series.</span></span> <span data-ttu-id="d8493-207">Но для целей прогноза временные срезы, используемые для прогнозирующих запросов, начинаются в конце исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="d8493-207">However, for the purpose of prediction, the time slices used for prediction queries start at the end of the original series.</span></span> <span data-ttu-id="d8493-208">Если при добавлении новых данных нужно получить только новые прогнозы, начальную точку необходимо указывать в виде номера временного среза.</span><span class="sxs-lookup"><span data-stu-id="d8493-208">If you want to obtain only the new predictions when you add the new data, you must specify the starting point as a number of time slices.</span></span> <span data-ttu-id="d8493-209">Например, если добавляются две новые точки данных и нужно сделать четыре новых прогноза, то необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d8493-209">For example, if you are adding two new data points and want to make four new predictions, you would do the following:</span></span>  
  
-   <span data-ttu-id="d8493-210">Создать PREDICTION JOIN для модели временных рядов и задать новые данные за два месяца.</span><span class="sxs-lookup"><span data-stu-id="d8493-210">Create a PREDICTION JOIN on a time series model, and specify two months of new data.</span></span>  
  
-   <span data-ttu-id="d8493-211">Запросить прогнозы для четырех временных срезов, где начальной точкой будет временной срез 3, а конечной — временной срез 6.</span><span class="sxs-lookup"><span data-stu-id="d8493-211">Request predictions for four time slices, where the starting point is 3, and the ending point is time slice 6.</span></span>  
  
 <span data-ttu-id="d8493-212">Иными словами, если новые данные содержат n срезов времени и вы запрашиваете прогнозы для шагов с 1 по n, прогнозы будут совпадать с периодом, аналогичным новым данным.</span><span class="sxs-lookup"><span data-stu-id="d8493-212">In other words, if your new data contains n time slices, and you request predictions for time steps 1 through n, the predictions will coincide with the same period as the new data.</span></span> <span data-ttu-id="d8493-213">Чтобы получить новые прогнозы для периодов времени, не охваченных имеющимися данными, необходимо либо начать прогнозирование с временного среза n+1 после нового ряда данных, либо убедиться в том, что запрашиваются дополнительные временные срезы.</span><span class="sxs-lookup"><span data-stu-id="d8493-213">To get new predictions for a time periods not covered by your data, you must either start predictions at the time slice n+1 after the new data series, or make sure that you request additional time slices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8493-214">Когда добавляются новые данные, исторические прогнозы невозможны.</span><span class="sxs-lookup"><span data-stu-id="d8493-214">You cannot make historical predictions when you add new data.</span></span>  
  
 <span data-ttu-id="d8493-215">В следующем примере продемонстрирована инструкция расширений интеллектуального анализа данных, которая позволяет получить только новые прогнозы для двух временных рядов предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="d8493-215">The following example shows the DMX statement that lets you get only the new predictions for the two series in the previous example.</span></span>  
  
```  
SELECT [Model Region],  
PredictTimeSeries([Quantity],3,6, EXTEND_MODEL_CASES) AS PredictQty  
FROM  
   [Forecasting_MIXED]  
NATURAL PREDICTION JOIN   
   SELECT 1 AS [ReportingDate],  
  '10' AS [Quantity],  
  'M200 Europe' AS [ModelRegion]  
UNION SELECT  
  2 AS [ReportingDate],  
  15 AS [Quantity]),  
  'M200 Europe' AS [ModelRegion]  
) AS t  
WHERE [ModelRegion] = 'M200 Europe'  
```  
  
 <span data-ttu-id="d8493-216">Результаты прогноза начинаются с временного среза 3, который идет после предоставленных новых данных за два месяца.</span><span class="sxs-lookup"><span data-stu-id="d8493-216">The prediction results start at time slice 3, which is after the 2 months of new data that you supplied.</span></span>  
  
 <span data-ttu-id="d8493-217">**Продукт и регион: M200 Европа**</span><span class="sxs-lookup"><span data-stu-id="d8493-217">**Product and Region: M200 Europe**</span></span>  
  
 <span data-ttu-id="d8493-218">Модель с обновленными данными (PredictTimeSeries с EXTEND_MODEL_CASES)</span><span class="sxs-lookup"><span data-stu-id="d8493-218">Model with updated data (PredictTimeSeries with EXTEND_MODEL_CASES)</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="d8493-219">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-219">M200 Europe</span></span>|<span data-ttu-id="d8493-220">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-220">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-221">72</span><span class="sxs-lookup"><span data-stu-id="d8493-221">72</span></span>|  
|<span data-ttu-id="d8493-222">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-222">M200 Europe</span></span>|<span data-ttu-id="d8493-223">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-223">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-224">69</span><span class="sxs-lookup"><span data-stu-id="d8493-224">69</span></span>|  
|<span data-ttu-id="d8493-225">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-225">M200 Europe</span></span>|<span data-ttu-id="d8493-226">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-226">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-227">68</span><span class="sxs-lookup"><span data-stu-id="d8493-227">68</span></span>|  
|<span data-ttu-id="d8493-228">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d8493-228">M200 Europe</span></span>|<span data-ttu-id="d8493-229">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d8493-229">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d8493-230">89</span><span class="sxs-lookup"><span data-stu-id="d8493-230">89</span></span>|  
  
## <a name="making-predictions-with-replace_model_cases"></a><span data-ttu-id="d8493-231">Прогнозирование с помощью REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d8493-231">Making Predictions with REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="d8493-232">Замена вариантов полезна в том случае, если необходимо обучить модель на одном наборе вариантов, а затем применить эту модель к другому ряду данных.</span><span class="sxs-lookup"><span data-stu-id="d8493-232">Replacing the model cases is useful when you want to train a model on one set of cases and then apply that model to a different data series.</span></span> <span data-ttu-id="d8493-233">Подробное пошаговое руководство по этому сценарию представлено на [занятии 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d8493-233">A detailed walkthrough of this scenario is presented in [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8493-234">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8493-234">See Also</span></span>  
 <span data-ttu-id="d8493-235">[Примеры запросов модели временных рядов](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="d8493-235">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="d8493-236">PredictTimeSeries (расширения интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="d8493-236">PredictTimeSeries &#40;DMX&#41;</span></span>](/sql/dmx/predicttimeseries-dmx)  
  
  
