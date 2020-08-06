---
title: Применение прогнозирующих функций к модели | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Model Prediction [Analysis Services], selecting mining models
ms.assetid: cf9a97e2-c249-441b-af12-c977c1a91c44
author: minewiskan
ms.author: owend
ms.openlocfilehash: fde9de00adaa1712a9db6e18aabc6a83dd660efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655444"
---
# <a name="apply-prediction-functions-to-a-model"></a><span data-ttu-id="29042-102">Применение функций прогнозирования к модели</span><span class="sxs-lookup"><span data-stu-id="29042-102">Apply Prediction Functions to a Model</span></span>
  <span data-ttu-id="29042-103">Чтобы создать прогнозирующий запрос, необходимо сначала выбрать модель интеллектуального анализа данных, на которой будет основан это запрос.</span><span class="sxs-lookup"><span data-stu-id="29042-103">To create a prediction query, you must first select the mining model on which the query will be based.</span></span> <span data-ttu-id="29042-104">Можно выбрать любую модель интеллектуального анализа данных, существующую в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="29042-104">You can select any mining model that exists in the current project.</span></span>  
  
 <span data-ttu-id="29042-105">Выбрав модель, добавьте в запрос *прогнозирующую функцию* .</span><span class="sxs-lookup"><span data-stu-id="29042-105">After you have selected a model, add a *prediction function* to the query.</span></span> <span data-ttu-id="29042-106">Он импортирует, чтобы понять, что функции прогнозирования используются для многих целей — Да, можно прогнозировать значения, но также можно получить связанную статистику, а также сведения, которые использовались при формировании прогноза.</span><span class="sxs-lookup"><span data-stu-id="29042-106">It is import to understand that prediction functions are used for many purposes-yes, you can predict values, but you can also get related statistics, as well as information that was used in generating the prediction.</span></span> <span data-ttu-id="29042-107">Прогнозирующие функции могут возвращать следующие типы значений.</span><span class="sxs-lookup"><span data-stu-id="29042-107">Prediction functions can return the following types of values:</span></span>  
  
-   <span data-ttu-id="29042-108">Имя прогнозируемого атрибута и значение, которое прогнозируется.</span><span class="sxs-lookup"><span data-stu-id="29042-108">The name of the predictable attribute, and the value that is predicted.</span></span>  
  
-   <span data-ttu-id="29042-109">Статистика по распределению и дисперсии предсказанных значений.</span><span class="sxs-lookup"><span data-stu-id="29042-109">Statistics about the distribution and variance of the predicted values.</span></span>  
  
-   <span data-ttu-id="29042-110">Вероятность заданного результата или всех возможных результатов.</span><span class="sxs-lookup"><span data-stu-id="29042-110">The probability of a specified outcome, or of all possible outcomes.</span></span>  
  
-   <span data-ttu-id="29042-111">Верхние или нижние оценки или значения.</span><span class="sxs-lookup"><span data-stu-id="29042-111">The top or bottom scores or values.</span></span>  
  
-   <span data-ttu-id="29042-112">Значения, связанные с заданным узлом, объектом или атрибутом.</span><span class="sxs-lookup"><span data-stu-id="29042-112">Values associated with a specified node, object, or attribute.</span></span>  
  
 <span data-ttu-id="29042-113">Существуют разные прогнозирующие функции, которые можно использовать, но необходимо выбрать функцию, соответствующую типу созданной модели.</span><span class="sxs-lookup"><span data-stu-id="29042-113">There is a wide variety of prediction functions that you can use, but you must choose the function that suits the type of model you created.</span></span> <span data-ttu-id="29042-114">Обычно этот выбор зависит от алгоритма, который использовался при создании модели.</span><span class="sxs-lookup"><span data-stu-id="29042-114">Usually this choice depends on the algorithm used to create the model.</span></span>  
  
-   <span data-ttu-id="29042-115">Список прогнозирующих функций, поддерживаемых почти всеми типами моделей, см. в разделе [Общие функции прогнозирования (расширения интеллектуального анализа данных)](/sql/dmx/general-prediction-functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="29042-115">For a list of the prediction functions that are supported for almost all model types, see [General Prediction Functions &#40;DMX&#41;](/sql/dmx/general-prediction-functions-dmx).</span></span>  
  
-   <span data-ttu-id="29042-116">Кроме того, отдельные алгоритмы поддерживают ряд специализированных функций.</span><span class="sxs-lookup"><span data-stu-id="29042-116">Additionally, individual algorithms support a variety of specialized functions.</span></span> <span data-ttu-id="29042-117">Например, если создается модель, основанная на алгоритме кластеризации Microsoft Clustering, можно использовать специализированные прогнозирующие функции для поиска информации о кластерах (расстояние значения данных от центроида кластера и т. п.).</span><span class="sxs-lookup"><span data-stu-id="29042-117">For example, if you create a mining model based on the Microsoft Clustering algorithm, you can use specialized prediction functions to find information about the clusters, such as the distance from a data value to the cluster centroid.</span></span>  
  
     <span data-ttu-id="29042-118">Примеры запросов к модели интеллектуального анализа данных определенного типа см. в справочнике по алгоритмам, в разделе [Алгоритмы интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="29042-118">For examples of how to query a specific type of mining model, see the algorithm reference topic, in [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="choose-a-mining-model-to-use-for-prediction"></a><span data-ttu-id="29042-119">Выберите модель интеллектуального анализа данных, которая должна использоваться для прогноза.</span><span class="sxs-lookup"><span data-stu-id="29042-119">Choose a mining model to use for prediction</span></span>  
  
1.  <span data-ttu-id="29042-120">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]щелкните модель правой кнопкой мыши и выберите пункт **Построить прогнозирующий запрос**.</span><span class="sxs-lookup"><span data-stu-id="29042-120">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, and select **Build Prediction Query**.</span></span>  
  
     <span data-ttu-id="29042-121">--ИЛИ--</span><span class="sxs-lookup"><span data-stu-id="29042-121">--OR --</span></span>  
  
     <span data-ttu-id="29042-122">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]щелкните вкладку **Прогнозирование моделей интеллектуального анализа данных**, а затем щелкните **Выбрать модель** в таблице  **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="29042-122">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the tab, **Mining Model Prediction**, and then click **Select Model** in the  **Mining Model** table.</span></span>  
  
2.  <span data-ttu-id="29042-123">В диалоговом окне **Выбор модели интеллектуального анализа данных** выберите модель интеллектуального анализа данных и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="29042-123">In the **Select Mining Model** dialog box, select a mining model, and then click **OK**.</span></span>  
  
     <span data-ttu-id="29042-124">Можно выбрать любую модель в текущей базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29042-124">You can choose any model within the current [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="29042-125">Для создания запроса с помощью модели, расположенной в другой базе данных, необходимо открыть новое окно запроса в контексте этой базы данных или открыть файл решения, который содержит эту модель.</span><span class="sxs-lookup"><span data-stu-id="29042-125">To create a query using a model in a different database, you must either open a new query window in the context of that database, or open the solution file that contains that model.</span></span>  
  
### <a name="add-prediction-functions-to-a-query"></a><span data-ttu-id="29042-126">Добавление прогнозирующих функций в запрос</span><span class="sxs-lookup"><span data-stu-id="29042-126">Add prediction functions to a query</span></span>  
  
1.  <span data-ttu-id="29042-127">В **построителе прогнозирующих запросов**задайте входные данные для прогнозирования, указав значения в диалоговом окне **Ввод одноэлементного запроса** или связав модель с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="29042-127">In the **Prediction Query Builder**, configure the input data used for prediction, either by providing values in the **Singleton Query Input** dialog box, or by mapping the model to an external data source.</span></span>  
  
     <span data-ttu-id="29042-128">Дополнительные сведения см. в разделе [Выбор и сопоставление входных данных для прогнозирующего запроса](choose-and-map-input-data-for-a-prediction-query.md).</span><span class="sxs-lookup"><span data-stu-id="29042-128">For more information, see [Choose and Map Input Data for a Prediction Query](choose-and-map-input-data-for-a-prediction-query.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="29042-129">Для создания прогнозов вводить данные необязательно.</span><span class="sxs-lookup"><span data-stu-id="29042-129">It is not required that you provide inputs to generate predictions.</span></span> <span data-ttu-id="29042-130">Если входных данных нет, алгоритм обычно возвращает наиболее вероятное прогнозируемое значение для всех возможных входных значений.</span><span class="sxs-lookup"><span data-stu-id="29042-130">When there is no input, the algorithm will typically return the mostly likely predicted value across all possible inputs.</span></span>  
  
2.  <span data-ttu-id="29042-131">Щелкните столбец **Источник** и выберите значение в списке.</span><span class="sxs-lookup"><span data-stu-id="29042-131">Click the **Source** column, and choose a value from the list:</span></span>  
  
    |||  
    |-|-|  
    |**\<model name>**|<span data-ttu-id="29042-132">Выберите этот параметр для включения значений из модели интеллектуального анализа данных в выходные данные.</span><span class="sxs-lookup"><span data-stu-id="29042-132">Select this option to include values from the mining model in the output.</span></span> <span data-ttu-id="29042-133">Можно добавить только прогнозируемые столбцы.</span><span class="sxs-lookup"><span data-stu-id="29042-133">You can only add predictable columns.</span></span><br /><br /> <span data-ttu-id="29042-134">Если добавляется столбец из модели, возвращаемый результат представляет собой список значений этого столбца, которые могут повторяться.</span><span class="sxs-lookup"><span data-stu-id="29042-134">When you add a column from the model, the result returned is the non-distinct list of values in that column.</span></span><br /><br /> <span data-ttu-id="29042-135">Столбцы, добавляемые с помощью этого параметра, включаются в предложение SELECT результирующей инструкции DMX.</span><span class="sxs-lookup"><span data-stu-id="29042-135">The columns that you add with this option are included in the SELECT portion of the resulting DMX statement.</span></span>|  
    |<span data-ttu-id="29042-136">**Prediction Function**</span><span class="sxs-lookup"><span data-stu-id="29042-136">**Prediction Function**</span></span>|<span data-ttu-id="29042-137">Выберите этот параметр для просмотра списка прогнозирующих функций.</span><span class="sxs-lookup"><span data-stu-id="29042-137">Select this option to browse a list of prediction functions.</span></span><br /><br /> <span data-ttu-id="29042-138">Значения выбранных функций добавляются в предложение SELECT результирующей инструкции DMX.</span><span class="sxs-lookup"><span data-stu-id="29042-138">The values or functions you select are added to the SELECT portion of the resulting DMX statement.</span></span><br /><br /> <span data-ttu-id="29042-139">Список прогнозирующих функций не фильтруется и не ограничивается выбранным типом модели.</span><span class="sxs-lookup"><span data-stu-id="29042-139">The list of prediction functions is not filtered or constrained by the type of model you have selected.</span></span> <span data-ttu-id="29042-140">Поэтому, если вы сомневаетесь, поддерживается ли функция для текущего типа модели, можно просто добавить функцию в список и посмотреть, возникла ли ошибка.</span><span class="sxs-lookup"><span data-stu-id="29042-140">Therefore, if you have any doubt about whether the function is supported for the current model type, you can just add the function to the list and see if there is an error.</span></span><br /><br /> <span data-ttu-id="29042-141">Элементы списка с символом доллара в начале (например, $AdjustedProbability) представляют столбцы вложенной таблицы, получаемой при использовании функции `PredictHistogram`.</span><span class="sxs-lookup"><span data-stu-id="29042-141">List items that are preceded by $ (such as $AdjustedProbability) represent columns from the nested table that is output when you use the function, `PredictHistogram`.</span></span> <span data-ttu-id="29042-142">Это сочетания клавиш, которые можно использовать, чтобы получить один столбец, а не вложенную таблицу.</span><span class="sxs-lookup"><span data-stu-id="29042-142">These are shortcuts that you can use to return a single column and not a nested table.</span></span>|  
    |<span data-ttu-id="29042-143">**Пользовательское выражение**</span><span class="sxs-lookup"><span data-stu-id="29042-143">**Custom Expression**</span></span>|<span data-ttu-id="29042-144">Выберите этот параметр для ввода пользовательского выражения, а затем назначьте псевдоним выходным данным.</span><span class="sxs-lookup"><span data-stu-id="29042-144">Select this option to type a custom expression and then assign an alias to the output.</span></span><br /><br /> <span data-ttu-id="29042-145">Пользовательское выражение добавляется в предложение SELECT конечного прогнозирующего запроса DMX.</span><span class="sxs-lookup"><span data-stu-id="29042-145">The custom expression is added to the SELECT portion of the resulting DMX prediction query.</span></span><br /><br /> <span data-ttu-id="29042-146">Этот параметр полезен, если нужно добавить текст для вывода с каждой строкой, вызывать функции VB или пользовательские хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="29042-146">This option is useful if you want to add text for output with each row, to call VB functions, or to call custom stored procedures.</span></span><br /><br /> <span data-ttu-id="29042-147">Сведения об использовании функций VBA и Excel из DMX см. в разделе [Функции VBA в DAX и многомерных выражениях](/sql/mdx/vba-functions-in-mdx-and-dax).</span><span class="sxs-lookup"><span data-stu-id="29042-147">For information about using VBA and Excel functions from DMX, see [VBA functions in MDX and DAX](/sql/mdx/vba-functions-in-mdx-and-dax).</span></span>|  
  
3.  <span data-ttu-id="29042-148">После добавления каждой функции или выражения перейдите в представление DMX, чтобы посмотреть, как функция добавляется в инструкцию DMX.</span><span class="sxs-lookup"><span data-stu-id="29042-148">After adding each function or expression, switch to DMX view to see how the function is added within the DMX statement.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="29042-149">Построитель прогнозирующих запросов не проверяет DMX до нажатия кнопки **Результаты**.</span><span class="sxs-lookup"><span data-stu-id="29042-149">The Prediction Query Builder does not validate the DMX until you click **Results**.</span></span> <span data-ttu-id="29042-150">Часто оказывается, что выражение, созданное построителем запросов, не является допустимой инструкцией DMX.</span><span class="sxs-lookup"><span data-stu-id="29042-150">Often, you will find that the expression that is produced by the query builder is not valid DMX.</span></span> <span data-ttu-id="29042-151">Типичные случаи — это указание столбца, не связанного с прогнозируемым столбцом, или попытка прогнозирования столбца во вложенной таблице, что требует вложенной инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="29042-151">Typical causes are referencing a column that is not related to the predictable column, or trying to predict a column in a nested table, which requires a sub-SELECT statement.</span></span> <span data-ttu-id="29042-152">В этот момент можно переключиться в представление DMX и продолжить редактирование инструкции.</span><span class="sxs-lookup"><span data-stu-id="29042-152">At this point, you can switch to DMX view and continue editing the statement.</span></span>  
  
### <a name="example-create-a-query-on-a-clustering-model"></a><span data-ttu-id="29042-153">Пример. Создание запроса на основе модели кластеризации</span><span class="sxs-lookup"><span data-stu-id="29042-153">Example: Create a query on a clustering model</span></span>  
  
1.  <span data-ttu-id="29042-154">Если у вас нет модели кластеризации для создания этого образца запроса, создайте модель [TM_Clustering] с помощью [Учебника по основам интеллектуального анализа данных](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="29042-154">If you do not have a clustering model available for building this sample query, create the model, [TM_Clustering], using the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span>  
  
2.  <span data-ttu-id="29042-155">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши модель [TM_Clustering] и выберите пункт **Построить прогнозирующий запрос**.</span><span class="sxs-lookup"><span data-stu-id="29042-155">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, [TM_Clustering], and select **Build Prediction Query**.</span></span>  
  
3.  <span data-ttu-id="29042-156">В меню **Модель интеллектуального анализа данных** выберите пункт **Одноэлементный запрос**.</span><span class="sxs-lookup"><span data-stu-id="29042-156">From the **Mining Model** menu, select **Singleton Query**.</span></span>  
  
4.  <span data-ttu-id="29042-157">В диалоговом окне **Ввод одноэлементного запроса** задайте следующие значения как входные:</span><span class="sxs-lookup"><span data-stu-id="29042-157">In the **Singleton Query Input** dialog box, set the following values as inputs:</span></span>  
  
    -   <span data-ttu-id="29042-158">Gender = M</span><span class="sxs-lookup"><span data-stu-id="29042-158">Gender = M</span></span>  
  
    -   <span data-ttu-id="29042-159">Расстояние до работы = 5—10 миль</span><span class="sxs-lookup"><span data-stu-id="29042-159">Commute Distance = 5-10 miles</span></span>  
  
5.  <span data-ttu-id="29042-160">В сетке запросов в списке столбца **Источник**выберите модель интеллектуального анализа данных TM_Clustering и добавьте столбец [Bike Buyer] ("Покупатель велосипеда").</span><span class="sxs-lookup"><span data-stu-id="29042-160">In the query grid, for **Source**, select TM_Clustering mining model, and add the column, [Bike Buyer].</span></span>  
  
6.  <span data-ttu-id="29042-161">В поле **источник**выберите **функция прогнозирование**и добавьте функцию `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="29042-161">For **Source**, select **Prediction Function**, and add the function, `Cluster`.</span></span>  
  
7.  <span data-ttu-id="29042-162">В поле « **источник**» выберите « **функция прогнозирования**», добавьте функцию `PredictSupport` и перетащите столбец модели [Bike Buyer] в область **критерий или аргумент** .</span><span class="sxs-lookup"><span data-stu-id="29042-162">For **Source**, select **Prediction Function**, add the function, `PredictSupport`, and drag the model column [Bike Buyer] into the **Criteria/Argument** box.</span></span> <span data-ttu-id="29042-163">В столбце **Псевдоним** введите **Support** (Поддержка).</span><span class="sxs-lookup"><span data-stu-id="29042-163">Type **Support** in the **Alias** column.</span></span>  
  
     <span data-ttu-id="29042-164">Скопируйте выражение, представляющее прогнозирующую функцию, и ссылку на столбец из поля **Критерий или аргумент** .</span><span class="sxs-lookup"><span data-stu-id="29042-164">Copy the expression representing the prediction function and column reference from the **Criteria/Argument** box.</span></span>  
  
8.  <span data-ttu-id="29042-165">В качестве **Источника**выберите **Пользовательское выражение**, введите псевдоним, а затем укажите функцию CEILING Excel с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="29042-165">For **Source**, select **Custom Expression**, type an alias, and then reference the Excel CEILING function by using the following syntax:</span></span>  
  
    ```  
    Excel![CEILING](<arguments) as <return type>  
    ```  
  
     <span data-ttu-id="29042-166">Вставьте ссылку на столбец в качестве аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="29042-166">Paste the column reference in as the argument to the function.</span></span>  
  
     <span data-ttu-id="29042-167">Например, следующее выражение возвращает значение CEILING для значения поддержки.</span><span class="sxs-lookup"><span data-stu-id="29042-167">For example, the following expression returns the CEILING of the support value:</span></span>  
  
    ```  
    EXCEL!CEILING(PredictSupport([TM_Clustering].[Bike Buyer]),2)  
    ```  
  
     <span data-ttu-id="29042-168">В столбце **Псевдоним** введите CEILING.</span><span class="sxs-lookup"><span data-stu-id="29042-168">Type CEILING in the **Alias** column.</span></span>  
  
9. <span data-ttu-id="29042-169">Щелкните **Переключиться в представление текста запроса** , чтобы увидеть созданную инструкцию DMX, а затем щелкните **Переключиться в представление результатов запроса** , чтобы увидеть выходные столбцы прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="29042-169">Click **Switch to query text view** to review the DMX statement that was generated, and then click **Switch to query result view** to see the columns output by the prediction query.</span></span>  
  
     <span data-ttu-id="29042-170">В следующей таблице показаны ожидаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="29042-170">The following table shows the expected results:</span></span>  
  
    |<span data-ttu-id="29042-171">Покупатель велосипеда</span><span class="sxs-lookup"><span data-stu-id="29042-171">Bike Buyer</span></span>|<span data-ttu-id="29042-172">$Cluster</span><span class="sxs-lookup"><span data-stu-id="29042-172">$Cluster</span></span>|<span data-ttu-id="29042-173">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="29042-173">SUPPORT</span></span>|<span data-ttu-id="29042-174">CEILING</span><span class="sxs-lookup"><span data-stu-id="29042-174">CEILING</span></span>|  
    |----------------|--------------|-------------|-------------|  
    |<span data-ttu-id="29042-175">0</span><span class="sxs-lookup"><span data-stu-id="29042-175">0</span></span>|<span data-ttu-id="29042-176">Кластер 8</span><span class="sxs-lookup"><span data-stu-id="29042-176">Cluster 8</span></span>|<span data-ttu-id="29042-177">954</span><span class="sxs-lookup"><span data-stu-id="29042-177">954</span></span>|<span data-ttu-id="29042-178">953.948638926372</span><span class="sxs-lookup"><span data-stu-id="29042-178">953.948638926372</span></span>|  
  
 <span data-ttu-id="29042-179">Если вы хотите добавить другие предложения в любом месте оператора, например, если хотите добавить предложение WHERE, вы не сможете добавить его с помощью сетки. Сначала необходимо переключиться на представление DMX.</span><span class="sxs-lookup"><span data-stu-id="29042-179">If you want to add other clauses elsewhere in the statement-for example, if you want to add a WHERE clause-you cannot add it by using the grid; you must switch to DMX view first.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29042-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="29042-180">See Also</span></span>  
 [<span data-ttu-id="29042-181">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="29042-181">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
