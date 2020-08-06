---
title: Прогнозирование временных рядов с использованием обновленных данных (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af73681d-ce1c-4b6e-b195-6df3d2fb5275
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2017defaba74071b1a12bee14a5d8907e4c71cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654638"
---
# <a name="time-series-predictions-using-updated-data-intermediate-data-mining-tutorial"></a><span data-ttu-id="d8c82-102">Прогнозы временных рядов с использованием обновленных данных (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="d8c82-102">Time Series Predictions using Updated Data (Intermediate Data Mining Tutorial)</span></span>
    
## <a name="creating-predictions-using-the-extended-sales-data"></a><span data-ttu-id="d8c82-103">Создание прогнозов с помощью расширенных сведений о продажах</span><span class="sxs-lookup"><span data-stu-id="d8c82-103">Creating Predictions using the Extended Sales Data</span></span>  
 <span data-ttu-id="d8c82-104">На этом занятии будет создан прогнозирующий запрос, который добавляет новые данные о продажах в модель.</span><span class="sxs-lookup"><span data-stu-id="d8c82-104">In this lesson, you will create a prediction query that adds the new sales data to the model.</span></span> <span data-ttu-id="d8c82-105">Дополняя модель новыми данными, можно получать актуальные прогнозы, которые включают последние точки данных.</span><span class="sxs-lookup"><span data-stu-id="d8c82-105">By extending the model with new data, you can get up-to-date predictions that include the newest data points.</span></span>  
  
 <span data-ttu-id="d8c82-106">Создание прогнозов временных рядов, использующих новые данные, несложно: просто добавьте параметр EXTEND_MODEL_CASES в функцию [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) , укажите источник новых данных и укажите, сколько прогнозов необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="d8c82-106">Creating time series predictions that use new data is easy: you simply add the parameter EXTEND_MODEL_CASES to the [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) function, specify the source of the new data, and specify how many predictions you want to get.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d8c82-107">Параметр EXTEND_MODEL_CASES не является обязательным. По умолчанию модель расширяется каждый раз при создании прогнозирующего запроса временных рядов путем соединения новых данных в качестве данных входа.</span><span class="sxs-lookup"><span data-stu-id="d8c82-107">The parameter EXTEND_MODEL_CASES is optional; by default the model is extended any time that you create a time series prediction query by joining new data as inputs.</span></span>  
  
#### <a name="to-build-the-prediction-query-and-add-new-data"></a><span data-ttu-id="d8c82-108">Создание прогнозирующего запроса и добавление новых данных</span><span class="sxs-lookup"><span data-stu-id="d8c82-108">To build the prediction query and add new data</span></span>  
  
1.  <span data-ttu-id="d8c82-109">Если модель еще не открыта, дважды щелкните структуру прогноза, а затем в конструкторе интеллектуального анализа данных перейдите на вкладку **Прогноз модели интеллектуального анализа** .</span><span class="sxs-lookup"><span data-stu-id="d8c82-109">If the model is not already open, double-click the Forecasting structure, and in Data Mining Designer, click the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="d8c82-110">На панели **модель интеллектуального анализа данных** должна быть уже выбрана прогнозная модель.</span><span class="sxs-lookup"><span data-stu-id="d8c82-110">In the **Mining Model** pane, the model Forecasting should already be selected.</span></span> <span data-ttu-id="d8c82-111">Если он не выбран, щелкните **выбрать модель**, а затем выберите модель прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="d8c82-111">If it is not selected, click **Select Model**, and then select the model, Forecasting.</span></span>  
  
3.  <span data-ttu-id="d8c82-112">На панели **Выбор входных таблиц** нажмите кнопку **выбрать таблицу вариантов**.</span><span class="sxs-lookup"><span data-stu-id="d8c82-112">In the **Select Input Table(s)** pane, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="d8c82-113">В диалоговом окне **Выбор таблицы** выберите источник данных [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8c82-113">In the **Select Table** dialog box, select the data source, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
     <span data-ttu-id="d8c82-114">В списке представлений источников данных выберите Невсалесдата и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d8c82-114">From the list of data source views, select NewSalesData and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d8c82-115">Щелкните правой кнопкой мыши поверхность области конструирования и выберите пункт **Изменить подключения**.</span><span class="sxs-lookup"><span data-stu-id="d8c82-115">Right-click the surface of the design area and select **Modify Connections**.</span></span>  
  
6.  <span data-ttu-id="d8c82-116">Используя диалоговое окно **Изменение сопоставления** , сопоставьте столбцы в модели со столбцами внешних данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d8c82-116">Using the **Modify Mapping** dialog box, map the columns in the model to the columns in the external data as follows:</span></span>  
  
    -   <span data-ttu-id="d8c82-117">Сопоставьте столбец ReportingDate в модели интеллектуального анализа данных со столбцом Невдате входными данными.</span><span class="sxs-lookup"><span data-stu-id="d8c82-117">Map the ReportingDate column in the mining model to the NewDate column in the input data.</span></span>  
  
    -   <span data-ttu-id="d8c82-118">Сопоставьте столбец Amount в модели интеллектуального анализа данных со столбцом Невамаунт во входные данные.</span><span class="sxs-lookup"><span data-stu-id="d8c82-118">Map the Amount column in the mining model to the NewAmount column in the input data.</span></span>  
  
    -   <span data-ttu-id="d8c82-119">Сопоставьте столбец Quantity в модели интеллектуального анализа данных со столбцом Невкти входными данными.</span><span class="sxs-lookup"><span data-stu-id="d8c82-119">Map the Quantity column in the mining model to the NewQty column in the input data.</span></span>  
  
    -   <span data-ttu-id="d8c82-120">Сопоставьте столбец ModelRegion в модели интеллектуального анализа данных со столбцом рядов во входные данные.</span><span class="sxs-lookup"><span data-stu-id="d8c82-120">Map the ModelRegion column in the mining model to the Series column in the input data.</span></span>  
  
7.  <span data-ttu-id="d8c82-121">Теперь вы создадите прогнозирующий запрос.</span><span class="sxs-lookup"><span data-stu-id="d8c82-121">Now you will build the prediction query.</span></span>  
  
     <span data-ttu-id="d8c82-122">Сначала добавьте столбец к прогнозирующему запросу, чтобы получить ряд, к которому относится прогноз.</span><span class="sxs-lookup"><span data-stu-id="d8c82-122">First, add a column to the prediction query to output the series the prediction applies to.</span></span>  
  
    1.  <span data-ttu-id="d8c82-123">В сетке щелкните первую пустую строку в разделе **источник**, а затем выберите прогнозирование.</span><span class="sxs-lookup"><span data-stu-id="d8c82-123">In the grid, click the first empty row, under **Source**, and then select Forecasting.</span></span>  
  
    2.  <span data-ttu-id="d8c82-124">В столбце **поле** выберите область модели, а для **псевдонима**введите `Model Region` .</span><span class="sxs-lookup"><span data-stu-id="d8c82-124">In the **Field** column, select Model Region and for **Alias**, type `Model Region`.</span></span>  
  
8.  <span data-ttu-id="d8c82-125">Далее добавьте и измените прогнозирующую функцию.</span><span class="sxs-lookup"><span data-stu-id="d8c82-125">Next, add and edit the prediction function.</span></span>  
  
    1.  <span data-ttu-id="d8c82-126">Щелкните пустую строку и в разделе **источник**выберите **функция прогнозирования**.</span><span class="sxs-lookup"><span data-stu-id="d8c82-126">Click an empty row, and under **Source**, select **Prediction Function**.</span></span>  
  
    2.  <span data-ttu-id="d8c82-127">Для **поля поле**выберите **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="d8c82-127">For **Field**, select **PredictTimeSeries**.</span></span>  
  
    3.  <span data-ttu-id="d8c82-128">В качестве **псевдонима**введите **прогнозируемые значения**.</span><span class="sxs-lookup"><span data-stu-id="d8c82-128">For **Alias**, type **Predicted Values**.</span></span>  
  
    4.  <span data-ttu-id="d8c82-129">Перетащите поле "количество" с панели **модель интеллектуального анализа данных** в столбец **критерий или аргумент** .</span><span class="sxs-lookup"><span data-stu-id="d8c82-129">Drag the field Quantity from the **Mining Model** pane into the **Criteria/Argument** column.</span></span>  
  
    5.  <span data-ttu-id="d8c82-130">В столбце **критерий или аргумент** после имени поля введите следующий текст: **5, EXTEND_MODEL_CASES**</span><span class="sxs-lookup"><span data-stu-id="d8c82-130">In the **Criteria/Argument** column, after the field name, type the following text:  **5,EXTEND_MODEL_CASES**</span></span>  
  
         <span data-ttu-id="d8c82-131">Полный текст текстового поля **критерий или аргумента** должен выглядеть следующим образом:`[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span><span class="sxs-lookup"><span data-stu-id="d8c82-131">The complete text of the **Criteria/Argument** text box should be as follows: `[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span></span>  
  
9. <span data-ttu-id="d8c82-132">Щелкните **результаты** и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="d8c82-132">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="d8c82-133">Прогноз начинается в июле (срез первого периода после исходных данных) и заканчивается в ноябре (срез пятого периода после исходных данных).</span><span class="sxs-lookup"><span data-stu-id="d8c82-133">The predictions begin in July (the first time slice after the end of the original data) and end at November (the fifth time slice after the end of the original data).</span></span>  
  
 <span data-ttu-id="d8c82-134">Как видно, чтобы эффективно использовать этот тип прогнозирующего запроса, нужно знать, когда завершаются старые данные, а также сколько имеется срезов в новых данных.</span><span class="sxs-lookup"><span data-stu-id="d8c82-134">You can see that to use this type of prediction query effectively, you need to know when the old data ends, as well as how many time slices there are in the new data.</span></span>  
  
 <span data-ttu-id="d8c82-135">Например, в этой модели ряд исходных данных завершился в июне, а данные были получены для июля, августа и сентября.</span><span class="sxs-lookup"><span data-stu-id="d8c82-135">For example, in this model, the original data series ended in June, and the data is for the months of July, August, and September.</span></span>  
  
 <span data-ttu-id="d8c82-136">Прогнозы, использующие параметр EXTEND_MODEL_CASES, всегда начинаются в конце ряда исходных данных.</span><span class="sxs-lookup"><span data-stu-id="d8c82-136">Predictions that use EXTEND_MODEL_CASES always begin at the end of the original data series.</span></span> <span data-ttu-id="d8c82-137">Поэтому, если нужно получить прогноз только для неизвестных месяцев, следует указать начальную и конечную точки прогноза.</span><span class="sxs-lookup"><span data-stu-id="d8c82-137">Therefore, if you want to get only the predictions for the unknown months, you need to specify the starting point and the end point for prediction.</span></span> <span data-ttu-id="d8c82-138">Оба значения указываются в качестве временных срезов в конце старых данных.</span><span class="sxs-lookup"><span data-stu-id="d8c82-138">Both values are specified as a number of time slices starting at the end of the old data.</span></span>  
  
 <span data-ttu-id="d8c82-139">В следующей процедуре показано, как это можно сделать.</span><span class="sxs-lookup"><span data-stu-id="d8c82-139">The following procedure demonstrates how to do this.</span></span>  
  
### <a name="change-the-start-and-end-points-of-the-predictions"></a><span data-ttu-id="d8c82-140">Изменение начальной и конечной точек прогноза</span><span class="sxs-lookup"><span data-stu-id="d8c82-140">Change the start and end points of the predictions</span></span>  
  
1.  <span data-ttu-id="d8c82-141">В конструктор запросов прогнозирования щелкните **запрос** , чтобы переключиться в представление DMX.</span><span class="sxs-lookup"><span data-stu-id="d8c82-141">In Prediction Query Builder, click **Query** to switch to DMX view.</span></span>  
  
2.  <span data-ttu-id="d8c82-142">Найдите DMX-инструкцию, содержащую функцию PredictTimeSeries, и измените ее следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d8c82-142">Locate the DMX statement that contains the PredictTimeSeries function and change it as follows:</span></span>  
  
     `PredictTimeSeries([Forecasting 12].[Quantity],4,6,EXTEND_MODEL_CASES)`  
  
3.  <span data-ttu-id="d8c82-143">Щелкните **результаты** и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="d8c82-143">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="d8c82-144">Теперь прогноз начинается в октябре (срез четвертого периода — начиная с конца исходных данных) и завершается в декабре (срез шестого периода — начиная с конца исходных данных).</span><span class="sxs-lookup"><span data-stu-id="d8c82-144">Now the predictions begin at October (the fourth time slice, counting from the end of the original data) and end at December (the sixth time slice, counting from the end of the original data).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d8c82-145">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="d8c82-145">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d8c82-146">Прогнозирование временных рядов с использованием замещения данных &#40;учебник по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="d8c82-146">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8c82-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8c82-147">See Also</span></span>  
 <span data-ttu-id="d8c82-148">[Технический справочник по алгоритму временных рядов (Майкрософт)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d8c82-148">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="d8c82-149">Содержимое моделей интеллектуального анализа данных для моделей временных рядов (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="d8c82-149">Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md)  
  
  
