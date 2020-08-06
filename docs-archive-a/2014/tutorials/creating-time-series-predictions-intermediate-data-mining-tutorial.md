---
title: Создание прогнозов временных рядов (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: fb22cffa-ac99-4d34-ac4a-9c93068e33e8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1175cdffd1512e0cb876b9565dd0727a9f094c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656957"
---
# <a name="creating-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="2a503-102">Создание прогнозов временных рядов (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="2a503-102">Creating Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="2a503-103">В ходе выполнения предыдущей задачи данного занятия была создана модель временных рядов и изучены результаты.</span><span class="sxs-lookup"><span data-stu-id="2a503-103">In the previous tasks in this lesson, you created a time series model and explored the results.</span></span> <span data-ttu-id="2a503-104">По умолчанию службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] всегда создают набор из пяти (5) прогнозов для модели временных рядов и отображают прогнозируемые значения в виде части диаграммы прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2a503-104">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] always creates a set of five (5) predictions for a time series model and displays the predicted values as part of the forecasting chart.</span></span> <span data-ttu-id="2a503-105">Однако можно также создавать прогнозы путем построения прогнозирующих запросов расширений интеллектуального анализа данных (DMX).</span><span class="sxs-lookup"><span data-stu-id="2a503-105">However, you can also create forecasts by building Data Mining Extensions (DMX) prediction queries.</span></span>  
  
 <span data-ttu-id="2a503-106">В ходе данной задачи будет создан прогнозирующий запрос, который сформирует такие же прогнозы, какие отображались ранее в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a503-106">In this task, you will create a prediction query that generates the same predictions that you saw in the viewer.</span></span> <span data-ttu-id="2a503-107">Для выполнения данной задачи необходимо пройти занятия учебника по интеллектуальному анализу данных (начальный уровень) и иметь навыки работы с построителем прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="2a503-107">This task assumes that you have already completed the lessons in the Basic Data Mining Tutorial and are familiar with how to use Prediction Query Builder.</span></span> <span data-ttu-id="2a503-108">Здесь будет показано, как можно создавать запросы, относящиеся к моделям временных рядов.</span><span class="sxs-lookup"><span data-stu-id="2a503-108">You will now learn how to create queries specific to time series models.</span></span>  
  
## <a name="creating-time-series-predictions"></a><span data-ttu-id="2a503-109">Создание прогнозов временных рядов</span><span class="sxs-lookup"><span data-stu-id="2a503-109">Creating Time Series Predictions</span></span>  
 <span data-ttu-id="2a503-110">Как правило, первым шагом в создании прогнозируемого запроса является выбор модели интеллектуального анализа данных и входной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a503-110">Typically, the first step in creating a prediction query is to select a mining model and input table.</span></span> <span data-ttu-id="2a503-111">Однако модель временных рядов не требует дополнительных входных данных для построения обычного прогноза.</span><span class="sxs-lookup"><span data-stu-id="2a503-111">However, a time series model does not require additional input for a regular prediction.</span></span> <span data-ttu-id="2a503-112">Поэтому нет необходимости указывать новый источник данных при создании прогнозов, за исключением случаев добавления данных в модель или замены данных.</span><span class="sxs-lookup"><span data-stu-id="2a503-112">Therefore, you do not need to specify a new source of data when making predictions, unless you are adding data to the model or replacing the data.</span></span>  
  
 <span data-ttu-id="2a503-113">В данном занятии необходимо указать количество этапов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2a503-113">For this lesson, you must specify the number of prediction steps.</span></span> <span data-ttu-id="2a503-114">Можно указать имя ряда, чтобы получить прогноз для определенного сочетания товара и региона.</span><span class="sxs-lookup"><span data-stu-id="2a503-114">You can specify the series name, to get a prediction for a particular combination of a product and a region.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="2a503-115">Выбор модели и входной таблицы</span><span class="sxs-lookup"><span data-stu-id="2a503-115">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="2a503-116">На вкладке **Прогноз модели интеллектуального анализа** в конструкторе интеллектуального анализа данных в поле **модель интеллектуального анализа** нажмите кнопку **выбрать модель**.</span><span class="sxs-lookup"><span data-stu-id="2a503-116">On the **Mining Model Prediction** tab of the Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="2a503-117">В диалоговом окне **Выбор модели интеллектуального анализа данных** разверните структуру прогнозирования, выберите модель **прогнозирования** из списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2a503-117">In the **Select Mining Model** dialog box, expand the Forecasting structure, select the **Forecasting** model from the list, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2a503-118">Не учитывать поле **Выбор входных таблиц** .</span><span class="sxs-lookup"><span data-stu-id="2a503-118">Ignore the **Select Input Table(s)** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a503-119">Для модели временных рядов не требуется указывать отдельные входные данные, за исключением случаев выполнения перекрестного прогноза.</span><span class="sxs-lookup"><span data-stu-id="2a503-119">For a time series model, you do not need to specify a separate input unless you are doing cross-prediction.</span></span>  
  
4.  <span data-ttu-id="2a503-120">В столбце **источник** в сетке на вкладке **Прогноз модели интеллектуального анализа данных** щелкните ячейку в первой пустой строке, а затем выберите **Прогноз модели интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="2a503-120">In the **Source** column, in the grid on the **Mining Model Prediction** tab, click the cell in the first empty row, and then select **Forecasting mining model**.</span></span>  
  
5.  <span data-ttu-id="2a503-121">В столбце **поле** выберите **область модели**.</span><span class="sxs-lookup"><span data-stu-id="2a503-121">In the **Field** column, select **Model Region**.</span></span>  
  
     <span data-ttu-id="2a503-122">В результате этого действия в прогнозирующий запрос будет добавлен идентификатор ряда с целью указания сочетания модели и региона, к которому будет относиться соответствующий прогноз.</span><span class="sxs-lookup"><span data-stu-id="2a503-122">This action adds the series identifier to the prediction query to indicate the combination of model and region to which the prediction applies.</span></span>  
  
6.  <span data-ttu-id="2a503-123">Щелкните следующую пустую строку в столбце **источник** , а затем выберите **функция прогнозирования**.</span><span class="sxs-lookup"><span data-stu-id="2a503-123">Click the next empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
7.  <span data-ttu-id="2a503-124">В столбце **поле** выберите **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="2a503-124">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a503-125">Также можно воспользоваться функцией `Predict` для моделей временных рядов.</span><span class="sxs-lookup"><span data-stu-id="2a503-125">You can also use the `Predict` function with time series models.</span></span> <span data-ttu-id="2a503-126">Однако по умолчанию функция Predict создает только один прогноз для каждого ряда.</span><span class="sxs-lookup"><span data-stu-id="2a503-126">However, by default, the Predict function creates only one prediction for each series.</span></span> <span data-ttu-id="2a503-127">Таким образом, чтобы указать несколько этапов прогнозирования, необходимо использовать функцию **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="2a503-127">Therefore, to specify multiple prediction steps, you must use the **PredictTimeSeries** function.</span></span>  
  
8.  <span data-ttu-id="2a503-128">На панели **модель интеллектуального анализа** данных выберите столбец модель интеллектуального анализа данных **размер.**</span><span class="sxs-lookup"><span data-stu-id="2a503-128">In the **Mining Model** pane, select the mining model column, **Amount.**</span></span> <span data-ttu-id="2a503-129">Перетащите параметр сумма в поле **критерий или аргументы** для функции **PredictTimeSeries** , которая была добавлена ранее.</span><span class="sxs-lookup"><span data-stu-id="2a503-129">Drag Amount to the **Criteria/Arguments** box for the **PredictTimeSeries** function that you added earlier.</span></span>  
  
9. <span data-ttu-id="2a503-130">Щелкните поле **критерий или аргументы** и введите запятую, а затем — **5**после имени поля.</span><span class="sxs-lookup"><span data-stu-id="2a503-130">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="2a503-131">Текст в поле **критерий или аргументы** теперь должен отображать следующее:</span><span class="sxs-lookup"><span data-stu-id="2a503-131">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[Amount],5`  
  
10. <span data-ttu-id="2a503-132">В столбце **псевдоним** введите `PredictAmount` .</span><span class="sxs-lookup"><span data-stu-id="2a503-132">In the **Alias** column, type `PredictAmount`.</span></span>  
  
11. <span data-ttu-id="2a503-133">Щелкните следующую пустую строку в **исходном** столбце, а затем снова выберите **функция прогнозирования** .</span><span class="sxs-lookup"><span data-stu-id="2a503-133">Click the next empty row in the **Source** column, and then select **Prediction Function** again.</span></span>  
  
12. <span data-ttu-id="2a503-134">В столбце **поле** выберите **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="2a503-134">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
13. <span data-ttu-id="2a503-135">На панели **модель интеллектуального анализа данных** выберите количество столбцов и перетащите его в поле **критерий или аргументы** второй функции **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="2a503-135">In the **Mining Model** pane, select the column Quantity, and then drag it into the **Criteria/Arguments** box for the second **PredictTimeSeries** function.</span></span>  
  
14. <span data-ttu-id="2a503-136">Щелкните поле **критерий или аргументы** и введите запятую, а затем — **5**после имени поля.</span><span class="sxs-lookup"><span data-stu-id="2a503-136">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="2a503-137">Текст в поле **критерий или аргументы** теперь должен отображать следующее:</span><span class="sxs-lookup"><span data-stu-id="2a503-137">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[ Quantity],5`  
  
15. <span data-ttu-id="2a503-138">В столбце **псевдоним** введите `PredictQuantity` .</span><span class="sxs-lookup"><span data-stu-id="2a503-138">In the **Alias** column, type `PredictQuantity`.</span></span>  
  
16. <span data-ttu-id="2a503-139">Щелкните **Переключиться в представление результатов запроса**.</span><span class="sxs-lookup"><span data-stu-id="2a503-139">Click **Switch to query result view**.</span></span>  
  
     <span data-ttu-id="2a503-140">Результаты запроса будут отображены в табличном формате.</span><span class="sxs-lookup"><span data-stu-id="2a503-140">The results of the query are displayed in tabular format.</span></span>  
  
 <span data-ttu-id="2a503-141">Итак, было создано три различных типа результатов в построителе запросов, один из которых использует значения столбца, а два других получают прогнозируемые значения из прогнозирующей функции.</span><span class="sxs-lookup"><span data-stu-id="2a503-141">Remember that you created three different types of results in the query builder, one that uses values from a column, and two that get predicted values from a prediction function.</span></span> <span data-ttu-id="2a503-142">Поэтому результаты запроса состоят из трех отдельных столбцов.</span><span class="sxs-lookup"><span data-stu-id="2a503-142">Therefore, the results of the query contain three separate columns.</span></span> <span data-ttu-id="2a503-143">В первом столбце содержится список сочетания товаров и регионов.</span><span class="sxs-lookup"><span data-stu-id="2a503-143">The first column contains the list of product and region combinations.</span></span> <span data-ttu-id="2a503-144">Во втором и третьем столбцах — по вложенной таблице с результатами прогнозов.</span><span class="sxs-lookup"><span data-stu-id="2a503-144">The second and third columns each contain a nested table of prediction results.</span></span> <span data-ttu-id="2a503-145">Каждая вложенная таблица содержит временные этапы и значения прогнозов, как, например, в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2a503-145">Each nested table contains the time step and predicted values, such as the following table:</span></span>  
  
 <span data-ttu-id="2a503-146">Результаты примера (суммы округлены до двух цифр после запятой):</span><span class="sxs-lookup"><span data-stu-id="2a503-146">Example results (amounts are truncated to two decimal places):</span></span>  
  
 <span data-ttu-id="2a503-147">**M200 Европа Предиктамаунт**</span><span class="sxs-lookup"><span data-stu-id="2a503-147">**M200 Europe PredictAmount**</span></span>  
  
|<span data-ttu-id="2a503-148">$TIME</span><span class="sxs-lookup"><span data-stu-id="2a503-148">$TIME</span></span>|<span data-ttu-id="2a503-149">"Сумма";</span><span class="sxs-lookup"><span data-stu-id="2a503-149">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="2a503-150">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-150">7/25/2008</span></span>|<span data-ttu-id="2a503-151">99978,00</span><span class="sxs-lookup"><span data-stu-id="2a503-151">99978.00</span></span>|  
|<span data-ttu-id="2a503-152">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-152">8/25/2008</span></span>|<span data-ttu-id="2a503-153">145575,07</span><span class="sxs-lookup"><span data-stu-id="2a503-153">145575.07</span></span>|  
|<span data-ttu-id="2a503-154">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-154">9/25/2008</span></span>|<span data-ttu-id="2a503-155">116835,19</span><span class="sxs-lookup"><span data-stu-id="2a503-155">116835.19</span></span>|  
|<span data-ttu-id="2a503-156">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-156">10/25/2008</span></span>|<span data-ttu-id="2a503-157">116537,38</span><span class="sxs-lookup"><span data-stu-id="2a503-157">116537.38</span></span>|  
|<span data-ttu-id="2a503-158">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-158">11/25/2008</span></span>|<span data-ttu-id="2a503-159">107760,55</span><span class="sxs-lookup"><span data-stu-id="2a503-159">107760.55</span></span>|  
  
 <span data-ttu-id="2a503-160">**M200 Европа Предикткуантити**</span><span class="sxs-lookup"><span data-stu-id="2a503-160">**M200 Europe PredictQuantity**</span></span>  
  
|<span data-ttu-id="2a503-161">$TIME</span><span class="sxs-lookup"><span data-stu-id="2a503-161">$TIME</span></span>|<span data-ttu-id="2a503-162">Количество</span><span class="sxs-lookup"><span data-stu-id="2a503-162">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="2a503-163">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-163">7/25/2008</span></span>|<span data-ttu-id="2a503-164">52</span><span class="sxs-lookup"><span data-stu-id="2a503-164">52</span></span>|  
|<span data-ttu-id="2a503-165">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-165">8/25/2008</span></span>|<span data-ttu-id="2a503-166">67</span><span class="sxs-lookup"><span data-stu-id="2a503-166">67</span></span>|  
|<span data-ttu-id="2a503-167">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-167">9/25/2008</span></span>|<span data-ttu-id="2a503-168">58</span><span class="sxs-lookup"><span data-stu-id="2a503-168">58</span></span>|  
|<span data-ttu-id="2a503-169">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-169">10/25/2008</span></span>|<span data-ttu-id="2a503-170">57</span><span class="sxs-lookup"><span data-stu-id="2a503-170">57</span></span>|  
|<span data-ttu-id="2a503-171">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-171">11/25/2008</span></span>|<span data-ttu-id="2a503-172">54</span><span class="sxs-lookup"><span data-stu-id="2a503-172">54</span></span>|  
  
 <span data-ttu-id="2a503-173">**M200 Северная Америка — Предиктамаунт**</span><span class="sxs-lookup"><span data-stu-id="2a503-173">**M200 North America - PredictAmount**</span></span>  
  
|<span data-ttu-id="2a503-174">$TIME</span><span class="sxs-lookup"><span data-stu-id="2a503-174">$TIME</span></span>|<span data-ttu-id="2a503-175">"Сумма";</span><span class="sxs-lookup"><span data-stu-id="2a503-175">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="2a503-176">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-176">7/25/2008</span></span>|<span data-ttu-id="2a503-177">348533,93</span><span class="sxs-lookup"><span data-stu-id="2a503-177">348533.93</span></span>|  
|<span data-ttu-id="2a503-178">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-178">8/25/2008</span></span>|<span data-ttu-id="2a503-179">340097,98</span><span class="sxs-lookup"><span data-stu-id="2a503-179">340097.98</span></span>|  
|<span data-ttu-id="2a503-180">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-180">9/25/2008</span></span>|<span data-ttu-id="2a503-181">257986,19</span><span class="sxs-lookup"><span data-stu-id="2a503-181">257986.19</span></span>|  
|<span data-ttu-id="2a503-182">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-182">10/25/2008</span></span>|<span data-ttu-id="2a503-183">374658,24</span><span class="sxs-lookup"><span data-stu-id="2a503-183">374658.24</span></span>|  
|<span data-ttu-id="2a503-184">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-184">11/25/2008</span></span>|<span data-ttu-id="2a503-185">379241,44</span><span class="sxs-lookup"><span data-stu-id="2a503-185">379241.44</span></span>|  
  
 <span data-ttu-id="2a503-186">**M200 Северная Америка — Предикткуантити**</span><span class="sxs-lookup"><span data-stu-id="2a503-186">**M200 North America - PredictQuantity**</span></span>  
  
|<span data-ttu-id="2a503-187">$TIME</span><span class="sxs-lookup"><span data-stu-id="2a503-187">$TIME</span></span>|<span data-ttu-id="2a503-188">Количество</span><span class="sxs-lookup"><span data-stu-id="2a503-188">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="2a503-189">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-189">7/25/2008</span></span>|<span data-ttu-id="2a503-190">272</span><span class="sxs-lookup"><span data-stu-id="2a503-190">272</span></span>|  
|<span data-ttu-id="2a503-191">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-191">8/25/2008</span></span>|<span data-ttu-id="2a503-192">152</span><span class="sxs-lookup"><span data-stu-id="2a503-192">152</span></span>|  
|<span data-ttu-id="2a503-193">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-193">9/25/2008</span></span>|<span data-ttu-id="2a503-194">250</span><span class="sxs-lookup"><span data-stu-id="2a503-194">250</span></span>|  
|<span data-ttu-id="2a503-195">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-195">10/25/2008</span></span>|<span data-ttu-id="2a503-196">181</span><span class="sxs-lookup"><span data-stu-id="2a503-196">181</span></span>|  
|<span data-ttu-id="2a503-197">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="2a503-197">11/25/2008</span></span>|<span data-ttu-id="2a503-198">290</span><span class="sxs-lookup"><span data-stu-id="2a503-198">290</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="2a503-199">Даты, используемые в образце базы данных, изменены для этой версии.</span><span class="sxs-lookup"><span data-stu-id="2a503-199">The dates that are used in the sample database have changed for this release.</span></span> <span data-ttu-id="2a503-200">Если используется более ранняя версия образца данных, могут появиться другие результаты.</span><span class="sxs-lookup"><span data-stu-id="2a503-200">If you are using an earlier version of the sample data, you might see different results.</span></span>  
  
## <a name="saving-the-prediction-results"></a><span data-ttu-id="2a503-201">Сохранение результатов прогноза</span><span class="sxs-lookup"><span data-stu-id="2a503-201">Saving the Prediction Results</span></span>  
 <span data-ttu-id="2a503-202">Есть несколько возможных вариантов использования результатов прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="2a503-202">You have several different options for using the prediction results.</span></span> <span data-ttu-id="2a503-203">Можно преобразовать результаты в плоский формат, скопировать данные из представления результатов и вставить в рабочий лист Excel или другой файл.</span><span class="sxs-lookup"><span data-stu-id="2a503-203">You can flatten the results, copy the data from the Results view, and paste it into an Excel worksheet or other file.</span></span>  
  
 <span data-ttu-id="2a503-204">Чтобы упростить процесс сохранения результатов, конструктор интеллектуального анализа данных также предоставляет возможность сохранения данных в новом представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="2a503-204">To simplify the process of saving results, Data Mining Designer also provides the ability to save the data to a data source view.</span></span> <span data-ttu-id="2a503-205">Функции сохранения результатов в представлении источника данных доступны только в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a503-205">The functionality for saving results to a data source view is available only in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2a503-206">Результаты могут храниться только в плоском формате.</span><span class="sxs-lookup"><span data-stu-id="2a503-206">The results can only be stored in a flattened format.</span></span>  
  
#### <a name="to-flatten-the-results-in-the-results-pane"></a><span data-ttu-id="2a503-207">Преобразование результатов в плоский формат на панели «Результаты»</span><span class="sxs-lookup"><span data-stu-id="2a503-207">To flatten the results in the Results pane</span></span>  
  
1.  <span data-ttu-id="2a503-208">В конструктор запросов прогнозирования щелкните **Переключиться в режим конструктора запросов**.</span><span class="sxs-lookup"><span data-stu-id="2a503-208">In the Prediction Query Builder, click **Switch to query design view**.</span></span>  
  
     <span data-ttu-id="2a503-209">После этого в представлении можно будет вручную изменить текст DMX-запроса.</span><span class="sxs-lookup"><span data-stu-id="2a503-209">The view changes to allow manual editing of the DMX query text.</span></span>  
  
2.  <span data-ttu-id="2a503-210">Введите ключевое слово `FLATTENED` после слова `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="2a503-210">Type the `FLATTENED` keyword after the `SELECT` keyword.</span></span> <span data-ttu-id="2a503-211">Полный текст запроса теперь должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2a503-211">The complete query text should be as follows:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    ```  
  
3.  <span data-ttu-id="2a503-212">Кроме того, можно указать предложение, которое будет ограничивать результаты, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="2a503-212">Optionally, you can type a clause to restrict the results, such as the following example:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    WHERE [Forecasting].[Model Region] = 'M200 North America'   
    OR [Forecasting].[Model Region] = 'M200 Europe'  
  
    ```  
  
4.  <span data-ttu-id="2a503-213">Щелкните **Переключиться в представление результатов запроса**.</span><span class="sxs-lookup"><span data-stu-id="2a503-213">Click **Switch to query result view**.</span></span>  
  
#### <a name="to-export-prediction-query-results"></a><span data-ttu-id="2a503-214">Экспорт результатов прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="2a503-214">To export prediction query results</span></span>  
  
1.  <span data-ttu-id="2a503-215">Нажмите кнопку **сохранить результаты запроса**.</span><span class="sxs-lookup"><span data-stu-id="2a503-215">Click **Save query results**.</span></span>  
  
2.  <span data-ttu-id="2a503-216">В диалоговом окне **Сохранение результата запроса интеллектуального анализа данных** выберите в поле **источник данных**значение [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a503-216">In the **Save Data Mining Query Result** dialog box, for **Data Source**, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="2a503-217">Также можно создать источник данных, если необходимо сохранить данные в другой реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="2a503-217">You can also create a data source if you want to save the data to a different relational database.</span></span>  
  
3.  <span data-ttu-id="2a503-218">В столбце **имя таблицы** введите новое имя временной таблицы, например **тестовые прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="2a503-218">In the **Table Name** column, type a new temporary table name, such as **Test Predictions**.</span></span>  
  
4.  <span data-ttu-id="2a503-219">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2a503-219">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a503-220">Чтобы просмотреть созданную таблицу, создайте соединение с компонентом Database Engine, на котором были сохранены данные, и сформируйте запрос.</span><span class="sxs-lookup"><span data-stu-id="2a503-220">To view the table that you created, create a connection to the database engine of the instance where you saved the data, and create a query.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="2a503-221">Заключение</span><span class="sxs-lookup"><span data-stu-id="2a503-221">Conclusion</span></span>  
 <span data-ttu-id="2a503-222">Было изучено создание базовой модели временных рядов, интерпретация прогнозов и создание прогнозов.</span><span class="sxs-lookup"><span data-stu-id="2a503-222">You have learned how to build a basic time series model, interpret the forecasts, and create predictions.</span></span>  
  
 <span data-ttu-id="2a503-223">Оставшиеся задания в этом учебнике не являются обязательными и описывают расширенное прогнозирование временных рядов.</span><span class="sxs-lookup"><span data-stu-id="2a503-223">The remaining tasks in this tutorial are optional, and describe advanced time series predictions.</span></span> <span data-ttu-id="2a503-224">В этих задачах будет изучено добавление новых данных в модель и создание прогнозов на основе расширенных рядов.</span><span class="sxs-lookup"><span data-stu-id="2a503-224">If you decide to go on, you will learn how to add new data to your model and create predictions on the extended series.</span></span> <span data-ttu-id="2a503-225">Будет также изучено выполнение перекрестного прогнозирования с использованием тренда в модели и заменой данных новым рядом данных.</span><span class="sxs-lookup"><span data-stu-id="2a503-225">You will also learn how to perform cross-prediction, by using the trend in the model but replacing the data with a new series of data.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="2a503-226">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="2a503-226">Next Lesson</span></span>  
 [<span data-ttu-id="2a503-227">Учебник по расширенному анализу временных рядов &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="2a503-227">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a503-228">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a503-228">See Also</span></span>  
 [<span data-ttu-id="2a503-229">Примеры запросов моделей временных рядов</span><span class="sxs-lookup"><span data-stu-id="2a503-229">Time Series Model Query Examples</span></span>](../../2014/analysis-services/data-mining/time-series-model-query-examples.md)  
  
  
