---
title: Занятие 4. Создание прогнозов временных рядов с помощью расширений интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6b883e43-209d-489a-8dc3-9349f88acae8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 772e5f5f71ca82dd18fec48730522c80e907414f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727497"
---
# <a name="lesson-4-creating-time-series-predictions-using-dmx"></a><span data-ttu-id="ea0ae-102">Занятие 4: Создание прогнозов на основе временных рядов с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ea0ae-102">Lesson 4: Creating Time Series Predictions Using DMX</span></span>
  <span data-ttu-id="ea0ae-103">На этом занятии и на следующем занятии будут использоваться расширения интеллектуального анализа данных для создания различных типов прогнозов на основе моделей временных рядов, созданных на [занятии 1. Создание модели и структуры интеллектуального анализа данных временных рядов](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) , а также [занятие 2. Добавление моделей интеллектуального анализа данных в структуру интеллектуального анализа временных рядов](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="ea0ae-103">In this lesson and the following lesson, you will use Data Mining Extensions (DMX) to create different types of predictions based on the time series models that you created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) and [Lesson 2: Adding Mining Models to the Time Series Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span></span>  
  
 <span data-ttu-id="ea0ae-104">Использование модели временных рядов дает много возможностей для выполнения прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-104">With a time series model, you have many options for making predictions:</span></span>  
  
-   <span data-ttu-id="ea0ae-105">Использование в модели интеллектуального анализа данных существующих закономерностей и данных.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-105">Use the existing patterns and data in the mining model</span></span>  
  
-   <span data-ttu-id="ea0ae-106">Использование в модели интеллектуального анализа данных существующих закономерностей, но предоставление новых данных.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-106">Use the existing patterns in the mining model but supply new data</span></span>  
  
-   <span data-ttu-id="ea0ae-107">Добавление в модель новых данных или обновление модели.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-107">Add new data to the model or update the model.</span></span>  
  
 <span data-ttu-id="ea0ae-108">Далее приведен синтаксис выполнения этих типов прогнозов.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-108">The syntax for making these prediction types is summarized below:</span></span>  
  
 <span data-ttu-id="ea0ae-109">Используемый по умолчанию прогноз временных рядов.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-109">Default time series prediction</span></span>  
 <span data-ttu-id="ea0ae-110">Используйте [PredictTimeSeries &#40;расширений интеллектуального анализа данных&#41;](/sql/dmx/predicttimeseries-dmx) , чтобы получить указанное количество прогнозов из обученной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-110">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) to return the specified number of predictions from the trained mining model.</span></span>  
  
 <span data-ttu-id="ea0ae-111">Например, см. раздел [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) или [примеры запросов модели временных рядов](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="ea0ae-111">For example, see [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) or [Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span></span>  
  
 <span data-ttu-id="ea0ae-112">EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="ea0ae-112">EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="ea0ae-113">Используйте [PredictTimeSeries &#40;расширений интеллектуального анализа данных&#41;](/sql/dmx/predicttimeseries-dmx) с аргументом EXTEND_MODEL_CASES, чтобы добавить новые данные, расширить ряд и создать прогнозы на основе обновленной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-113">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the EXTEND_MODEL_CASES argument to add new data, extend the series, and create predictions based on the updated mining model.</span></span>  
  
 <span data-ttu-id="ea0ae-114">Этот учебник содержит пример использования аргумента EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-114">This tutorial contains an example of how to use EXTEND_MODEL_CASES.</span></span>  
  
 <span data-ttu-id="ea0ae-115">REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="ea0ae-115">REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="ea0ae-116">Используйте [PredictTimeSeries &#40;расширений интеллектуального анализа данных&#41;](/sql/dmx/predicttimeseries-dmx) с аргументом REPLACE_MODEL_CASES, чтобы заменить исходные данные на новый ряд данных, а затем создайте прогнозы на основе применения шаблонов в модели интеллектуального анализа данных к новым рядам.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-116">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the REPLACE_MODEL_CASES argument to replace the original data with a new data series, and then create predictions based on applying the patterns in the mining model to the new data series.</span></span>  
  
 <span data-ttu-id="ea0ae-117">Пример использования REPLACE_MODEL_CASES см. в разделе [занятие 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ea0ae-117">For an example of how to use REPLACE_MODEL_CASES, see [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="ea0ae-118">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="ea0ae-118">Lesson Tasks</span></span>  
 <span data-ttu-id="ea0ae-119">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-119">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="ea0ae-120">Создание запроса для получения используемых по умолчанию прогнозов, основанных на существующих данных.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-120">Create a query to get the default predictions based on existing data.</span></span>  
  
 <span data-ttu-id="ea0ae-121">На следующем занятии будут выполнены следующие связанные задачи.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-121">In the following lesson you will perform the following related tasks:</span></span>  
  
-   <span data-ttu-id="ea0ae-122">Создание запроса для предоставления новых данных и получения обновленных прогнозов.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-122">Create a query to supply new data and get updated predictions.</span></span>  
  
 <span data-ttu-id="ea0ae-123">Наряду с созданием запросов вручную, при помощи расширений интеллектуального анализа данных, можно также создавать прогнозы в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], с помощью построителя прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-123">In addition to creating queries manually by using DMX, you can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="simple-time-series-prediction-query"></a><span data-ttu-id="ea0ae-124">Простой прогнозирующий запрос временных рядов</span><span class="sxs-lookup"><span data-stu-id="ea0ae-124">Simple Time Series Prediction Query</span></span>  
 <span data-ttu-id="ea0ae-125">На первом шаге используется инструкция `SELECT FROM` совместно с функцией `PredictTimeSeries` для создания прогноза временных рядов.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-125">The first step is to use the `SELECT FROM` statement together with the `PredictTimeSeries` function to create time series predictions.</span></span> <span data-ttu-id="ea0ae-126">Модели временных рядов поддерживают упрощенный синтаксис создания прогнозов: нет необходимости предоставлять входные данные, нужно только задать количество создаваемых прогнозов.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-126">Time series models support a simplified syntax for creating predictions: you do not need to supply any inputs, but only have to specify the number of predictions to create.</span></span> <span data-ttu-id="ea0ae-127">В следующем фрагменте показан общий пример инструкции, которая будет использоваться в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-127">The following is a generic example of the statement you will use:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model name>]   
WHERE [<criteria>]  
```  
  
 <span data-ttu-id="ea0ae-128">Список выбора может содержать столбцы из модели, например имя линии продукта, для которой создаются прогнозы, или прогнозирующие функции, такие как [запаздывание &#40;dmx&#41;](/sql/dmx/lag-dmx) или [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), которые предназначены специально для моделей интеллектуального анализа данных временных рядов.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-128">The select list can contain columns from the model, such as the name of the product line that you are creating the predictions for, or prediction functions, such as [Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) or [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), which are specifically for time series mining models.</span></span>  
  
#### <a name="to-create-a-simple-time-series-prediction-query"></a><span data-ttu-id="ea0ae-129">Создание простого запроса прогнозирования временного ряда</span><span class="sxs-lookup"><span data-stu-id="ea0ae-129">To create a simple time series prediction query</span></span>  
  
1.  <span data-ttu-id="ea0ae-130">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-130">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="ea0ae-131">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-131">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="ea0ae-132">Скопируйте общий пример инструкции в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-132">Copy the generic example of the statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="ea0ae-133">Вместо</span><span class="sxs-lookup"><span data-stu-id="ea0ae-133">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="ea0ae-134">на:</span><span class="sxs-lookup"><span data-stu-id="ea0ae-134">with:</span></span>  
  
    ```  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    ```  
  
     <span data-ttu-id="ea0ae-135">В первой строке извлекается значение из модели интеллектуального анализа данных, которая идентифицирует ряд.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-135">The first line retrieves a value from the mining model that identifies the series.</span></span>  
  
     <span data-ttu-id="ea0ae-136">Во второй и третьей строке используется функция `PredictTimeSeries`.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-136">The second and third lines use the `PredictTimeSeries` function.</span></span> <span data-ttu-id="ea0ae-137">В каждой строке предсказание выполняется для разных атрибутов, для `[Quantity]` или `[Amount]`.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-137">Each line predicts a different attribute, `[Quantity]` or `[Amount]`.</span></span> <span data-ttu-id="ea0ae-138">Числа после имен прогнозируемых атрибутов указывают количество временных шагов, необходимых для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-138">The numbers after the names of the predictable attributes specify the number of time steps to predict.</span></span>  
  
     <span data-ttu-id="ea0ae-139">Предложение `AS` используется для предоставления имени столбца, возвращаемого каждой прогнозирующей функцией.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-139">The `AS` clause is used to provide a name for the column that is returned by each prediction function.</span></span> <span data-ttu-id="ea0ae-140">Если псевдоним не указывается, по умолчанию возвращаются оба столбца с меткой `Expression`.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-140">If you do not supply an alias, by default both columns are returned with the label, `Expression`.</span></span>  
  
4.  <span data-ttu-id="ea0ae-141">Вместо</span><span class="sxs-lookup"><span data-stu-id="ea0ae-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="ea0ae-142">на:</span><span class="sxs-lookup"><span data-stu-id="ea0ae-142">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="ea0ae-143">Вместо</span><span class="sxs-lookup"><span data-stu-id="ea0ae-143">Replace the following:</span></span>  
  
    ```  
    WHERE [criteria>]   
    ```  
  
     <span data-ttu-id="ea0ae-144">на:</span><span class="sxs-lookup"><span data-stu-id="ea0ae-144">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="ea0ae-145">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-145">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    FROM   
    [Forecasting_MIXED]  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
6.  <span data-ttu-id="ea0ae-146">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="ea0ae-147">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `SimpleTimeSeriesPrediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="ea0ae-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SimpleTimeSeriesPrediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="ea0ae-148">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="ea0ae-148">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="ea0ae-149">Запрос возвращает 6 прогнозов для каждого из двух сочетаний продукта и региона, указанных в предложении `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-149">The query returns 6 predictions for each of the two combinations of product and region that are specified in the `WHERE` clause.</span></span>  
  
 <span data-ttu-id="ea0ae-150">На следующем занятии будет создан запрос, предоставляющий модели новые данные, и будет выполнено сравнение результатов этого прогноза с результатами только что созданного прогноза.</span><span class="sxs-lookup"><span data-stu-id="ea0ae-150">In the next lesson, you will create a query that supplies new data to the model, and compare the results of that prediction with the one you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ea0ae-151">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="ea0ae-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ea0ae-152">Занятие 5.: Расширение модели временных рядов</span><span class="sxs-lookup"><span data-stu-id="ea0ae-152">Lesson 5: Extending the Time Series Model</span></span>](../../2014/tutorials/lesson-5-extending-the-time-series-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea0ae-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea0ae-153">See Also</span></span>  
 <span data-ttu-id="ea0ae-154">[PredictTimeSeries &#40;расширений интеллектуального анализа данных&#41;](/sql/dmx/predicttimeseries-dmx) </span><span class="sxs-lookup"><span data-stu-id="ea0ae-154">[PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) </span></span>  
 <span data-ttu-id="ea0ae-155">[Запаздывание &#40;&#41;расширений интеллектуального анализа данных](/sql/dmx/lag-dmx) </span><span class="sxs-lookup"><span data-stu-id="ea0ae-155">[Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) </span></span>  
 <span data-ttu-id="ea0ae-156">[Примеры запросов модели временных рядов](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="ea0ae-156">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="ea0ae-157">Занятие 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ea0ae-157">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
  
