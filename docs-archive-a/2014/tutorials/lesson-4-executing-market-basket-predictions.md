---
title: Занятие 4. исполнение прогнозов потребительской корзины | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b3238f1b-ea04-4253-ade2-838a806b62fe
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3b49fc242eb8b2242269c5af33cc094937bbe0de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658588"
---
# <a name="lesson-4-executing-market-basket-predictions"></a><span data-ttu-id="7dd58-102">Занятие 4: Прогнозирование покупательского поведения</span><span class="sxs-lookup"><span data-stu-id="7dd58-102">Lesson 4: Executing Market Basket Predictions</span></span>
  <span data-ttu-id="7dd58-103">На этом занятии будет использоваться `SELECT` Инструкция DMX для создания прогнозов на основе моделей взаимосвязей, созданных на [занятии 2. Добавление моделей интеллектуального анализа данных в структуру интеллектуального анализа данных для рынка](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="7dd58-103">In this lesson, you will use the DMX `SELECT` statement to create predictions based on the association models you created in [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="7dd58-104">Прогнозирующий запрос создается с помощью инструкции расширений интеллектуального анализа данных `SELECT` с добавлением предложения `PREDICTION JOIN`.</span><span class="sxs-lookup"><span data-stu-id="7dd58-104">A prediction query is created by using the DMX `SELECT` statement and adding a `PREDICTION JOIN` clause.</span></span> <span data-ttu-id="7dd58-105">Дополнительные сведения о синтаксисе прогнозирующего подключения см. в разделе [SELECT FROM &#60;model&#62; PREDICTION join &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span><span class="sxs-lookup"><span data-stu-id="7dd58-105">For more information about the syntax of a prediction join, see [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span></span>  
  
 <span data-ttu-id="7dd58-106">Форма **Выбор из \<model> прогнозного подключения** `SELECT` инструкции содержит три части:</span><span class="sxs-lookup"><span data-stu-id="7dd58-106">The **SELECT FROM \<model> PREDICTION JOIN** form of the `SELECT` statement contains three parts:</span></span>  
  
-   <span data-ttu-id="7dd58-107">Список столбцов модели интеллектуального анализа и функции прогнозирования, возвращаемые в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="7dd58-107">A list of the mining model columns and prediction functions that are returned in the result set.</span></span> <span data-ttu-id="7dd58-108">В этом списке также могут содержаться входные столбцы источника данных.</span><span class="sxs-lookup"><span data-stu-id="7dd58-108">This list can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="7dd58-109">Исходный запрос, определяющий данные, которые используются при создании прогноза.</span><span class="sxs-lookup"><span data-stu-id="7dd58-109">A source query that defines the data that is being used to create a prediction.</span></span> <span data-ttu-id="7dd58-110">Например, если в пакете создается много прогнозов, исходный запрос может получить список клиентов.</span><span class="sxs-lookup"><span data-stu-id="7dd58-110">For example, if you are creating many predictions in a batch, the source query could retrieve a list of customers.</span></span>  
  
-   <span data-ttu-id="7dd58-111">Сопоставление столбцов модели интеллектуального анализа данных с исходными данными.</span><span class="sxs-lookup"><span data-stu-id="7dd58-111">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="7dd58-112">При совпадении имен столбцов можно использовать синтаксис `NATURAL PREDICTION JOIN` и пропустить процесс сопоставления столбцов.</span><span class="sxs-lookup"><span data-stu-id="7dd58-112">If the columns names match, you can use the `NATURAL PREDICTION JOIN` syntax and omit the column mappings.</span></span>  
  
 <span data-ttu-id="7dd58-113">Запрос можно расширить функциями прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="7dd58-113">You can enhance the query by using prediction functions.</span></span> <span data-ttu-id="7dd58-114">Функции прогнозирования предоставляют дополнительные данные, например вероятность возникновения предсказанного события, а также поддержку прогнозирования на наборе обучающих данных.</span><span class="sxs-lookup"><span data-stu-id="7dd58-114">Prediction functions provide additional information, such as the probability of a prediction occurring, or the support for a prediction in the training dataset.</span></span> <span data-ttu-id="7dd58-115">Дополнительные сведения о функциях прогнозирования см. в разделе [функции &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="7dd58-115">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="7dd58-116">Для создания прогнозирующих запросов можно также использовать построитель прогнозирующих запросов среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd58-116">You can also use the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create prediction queries.</span></span>  
  
## <a name="singleton-prediction-join-statement"></a><span data-ttu-id="7dd58-117">Одноэлементная инструкция PREDICTION JOIN</span><span class="sxs-lookup"><span data-stu-id="7dd58-117">Singleton PREDICTION JOIN Statement</span></span>  
 <span data-ttu-id="7dd58-118">Первым шагом является создание одноэлементного запроса с помощью синтаксиса **выборки из \<model> прогнозируемого объединения** и предоставление одного набора значений в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="7dd58-118">The first step is to create a singleton query, by using the **SELECT FROM \<model> PREDICTION JOIN** syntax and supplying a single set of values as input.</span></span> <span data-ttu-id="7dd58-119">В следующем фрагменте показан общий пример одноэлементной инструкции:</span><span class="sxs-lookup"><span data-stu-id="7dd58-119">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list>  
    FROM [<mining model>]   
[NATURAL] PREDICTION JOIN  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
AS [<input alias>]  
```  
  
 <span data-ttu-id="7dd58-120">В первой строке кода определяются столбцы модели интеллектуального анализа, которые возвращают запрос, а также указывается имя модели интеллектуального анализа данных, которая использовалась для создания прогноза:</span><span class="sxs-lookup"><span data-stu-id="7dd58-120">The first line of the code defines the columns from the mining model that the query returns, and specifies the name of the mining model used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>]   
```  
  
 <span data-ttu-id="7dd58-121">В следующей строке кода указывается операция, которая будет выполнена.</span><span class="sxs-lookup"><span data-stu-id="7dd58-121">The next line of the code indicates the operation to perform.</span></span> <span data-ttu-id="7dd58-122">Поскольку имена столбцов и их значения будут введены именно так, как это требуется для модели, можно использовать синтаксис `NATURAL PREDICTION JOIN`.</span><span class="sxs-lookup"><span data-stu-id="7dd58-122">Because you will specify values for each of the columns and type the column names exactly so as to match the model, you can use the `NATURAL PREDICTION JOIN` syntax.</span></span> <span data-ttu-id="7dd58-123">Однако если имена столбцов отличались друг от друга, потребуется указать сопоставления между столбцами в модели и столбцами в новых данных путем добавления предложения `ON`.</span><span class="sxs-lookup"><span data-stu-id="7dd58-123">However, if the column names were different, you would have to specify mappings between the columns in the model and the columns in the new data by adding an `ON` clause.</span></span>  
  
```  
[NATURAL] PREDICTION JOIN  
```  
  
 <span data-ttu-id="7dd58-124">Следующие строки кода определяют товар в корзине покупателя, на основе которого будет сформирован прогноз относительно следующих покупок данного клиента:</span><span class="sxs-lookup"><span data-stu-id="7dd58-124">The next lines of the code define the products in the shopping cart that will be used to predict additional products that a customer will add:</span></span>  
  
```  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="7dd58-125">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="7dd58-125">Lesson Tasks</span></span>  
 <span data-ttu-id="7dd58-126">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="7dd58-126">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="7dd58-127">Создание запроса для прогнозирования последующих возможных покупок клиента на основе данных о позициях товара, уже находящихся в его корзине.</span><span class="sxs-lookup"><span data-stu-id="7dd58-127">Create a query that predicts what other items a customer will likely purchase, based on items already existing in their shopping cart.</span></span> <span data-ttu-id="7dd58-128">Этот запрос будет создан с использованием модели интеллектуального анализа данных с *MINIMUM_PROBABILITY*по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7dd58-128">You will create this query by using the mining model with the default *MINIMUM_PROBABILITY*.</span></span>  
  
-   <span data-ttu-id="7dd58-129">Создание запроса для прогнозирования последующих возможных покупок клиента на основе данных о позициях товара, уже находящихся в его корзине.</span><span class="sxs-lookup"><span data-stu-id="7dd58-129">Create a query that predicts what other items a customer will likely purchase based on items already existing in their shopping cart.</span></span> <span data-ttu-id="7dd58-130">Этот запрос основан на другой модели, в которой *MINIMUM_PROBABILITY* установлен в значение 0,01.</span><span class="sxs-lookup"><span data-stu-id="7dd58-130">This query is based on a different model, in which *MINIMUM_PROBABILITY* has been set to 0.01.</span></span> <span data-ttu-id="7dd58-131">Поскольку значение по умолчанию для *MINIMUM_PROBABILITY* в моделях взаимосвязей равно 0,3, запрос в этой модели должен возвращать больше элементов, чем запрос по модели по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7dd58-131">Because the default value for *MINIMUM_PROBABILITY* in association models is 0.3, the query on this model should return more possible items than the query on the default model.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-the-default-minimum_probability"></a><span data-ttu-id="7dd58-132">Формирование прогноза с помощью модели со значением свойства MINIMUM_PROBABILITY по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7dd58-132">Create a Prediction by Using a Model with the Default MINIMUM_PROBABILITY</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="7dd58-133">Создание запроса взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="7dd58-133">To create an association query</span></span>  
  
1.  <span data-ttu-id="7dd58-134">В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**и выберите **DMX (расширения интеллектуального анализа данных** ), чтобы открыть редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="7dd58-134">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="7dd58-135">Скопируйте общий пример инструкции `PREDICTION JOIN` в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="7dd58-135">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="7dd58-136">Вместо</span><span class="sxs-lookup"><span data-stu-id="7dd58-136">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="7dd58-137">на:</span><span class="sxs-lookup"><span data-stu-id="7dd58-137">with:</span></span>  
  
    ```  
    PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
     <span data-ttu-id="7dd58-138">Можно просто включить имя столбца [Products], но с помощью функции [прогнозирования &#40;расширений интеллектуального анализа данных&#41;](/sql/dmx/predict-dmx) можно ограничить количество продуктов, возвращаемых алгоритмом, на три.</span><span class="sxs-lookup"><span data-stu-id="7dd58-138">You could just include the column name [Products], but by using the [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) function, you can limit the number of products that are returned by the algorithm to three.</span></span> <span data-ttu-id="7dd58-139">С помощью инструкции `INCLUDE_STATISTICS` можно получить сведения о поддержке, вероятности и скорректированной вероятности для каждой позиции товара.</span><span class="sxs-lookup"><span data-stu-id="7dd58-139">You can also use `INCLUDE_STATISTICS`, which returns the support, probability, and adjusted probability for each product.</span></span> <span data-ttu-id="7dd58-140">Такие статистические данные позволяют оценить точность прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="7dd58-140">These statistics help you rate the accuracy of the prediction.</span></span>  
  
4.  <span data-ttu-id="7dd58-141">Вместо</span><span class="sxs-lookup"><span data-stu-id="7dd58-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="7dd58-142">на:</span><span class="sxs-lookup"><span data-stu-id="7dd58-142">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="7dd58-143">Вместо</span><span class="sxs-lookup"><span data-stu-id="7dd58-143">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="7dd58-144">на:</span><span class="sxs-lookup"><span data-stu-id="7dd58-144">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="7dd58-145">Здесь инструкция `UNION` используется для указания трех позиций товара, которые должны быть добавлены в корзину вместе с прогнозируемыми товарами.</span><span class="sxs-lookup"><span data-stu-id="7dd58-145">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="7dd58-146">Столбец Model инструкции `SELECT` относится к столбцу модели, содержащемуся во вложенной таблице товаров.</span><span class="sxs-lookup"><span data-stu-id="7dd58-146">The Model column in the `SELECT` statement corresponds to the model column that is contained in the nested products table.</span></span>  
  
     <span data-ttu-id="7dd58-147">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7dd58-147">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Default Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="7dd58-148">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="7dd58-148">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="7dd58-149">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="7dd58-149">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="7dd58-150">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="7dd58-150">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="7dd58-151">Запрос возвращает таблицу, содержащую три продукта: HL Mountain, крыльев Set-Mountain и ML Mountain.</span><span class="sxs-lookup"><span data-stu-id="7dd58-151">The query returns a table that contains three products: HL Mountain Tire, Fender Set - Mountain, and ML Mountain Tire.</span></span> <span data-ttu-id="7dd58-152">В таблице эти продукты перечислены в порядке их вероятности.</span><span class="sxs-lookup"><span data-stu-id="7dd58-152">The table lists these returned products in order of probability.</span></span> <span data-ttu-id="7dd58-153">Возвращаемый продукт, который имеет наибольшую вероятность попасть в один и тот же список покупок с тремя продуктами, перечисленными в запросе, отображается в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="7dd58-153">The returned product that is most likely to be included in the same shopping cart as the three products specified in the query appears at the top of the table.</span></span> <span data-ttu-id="7dd58-154">Два продукта, расположенные ниже, — следующие по вероятности включения в список покупок.</span><span class="sxs-lookup"><span data-stu-id="7dd58-154">The two products that follow are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="7dd58-155">Кроме этого, в таблице содержатся статистические данные, описывающие точность прогноза.</span><span class="sxs-lookup"><span data-stu-id="7dd58-155">The table also contains statistics describing the accuracy of the prediction.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-a-minimum_probability-of-001"></a><span data-ttu-id="7dd58-156">Формирование прогноза с помощью модели со значением 0,01 у свойства MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="7dd58-156">Create a Prediction by Using a Model with a MINIMUM_PROBABILITY of 0.01</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="7dd58-157">Создание запроса взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="7dd58-157">To create an association query</span></span>  
  
1.  <span data-ttu-id="7dd58-158">В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**и выберите **DMX (расширения интеллектуального анализа данных** ), чтобы открыть редактор запросов.</span><span class="sxs-lookup"><span data-stu-id="7dd58-158">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="7dd58-159">Скопируйте общий пример инструкции `PREDICTION JOIN` в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="7dd58-159">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="7dd58-160">Вместо</span><span class="sxs-lookup"><span data-stu-id="7dd58-160">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="7dd58-161">на:</span><span class="sxs-lookup"><span data-stu-id="7dd58-161">with:</span></span>  
  
    ```  
    PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
4.  <span data-ttu-id="7dd58-162">Вместо</span><span class="sxs-lookup"><span data-stu-id="7dd58-162">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="7dd58-163">на:</span><span class="sxs-lookup"><span data-stu-id="7dd58-163">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="7dd58-164">Вместо</span><span class="sxs-lookup"><span data-stu-id="7dd58-164">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="7dd58-165">на:</span><span class="sxs-lookup"><span data-stu-id="7dd58-165">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="7dd58-166">Здесь инструкция `UNION` используется для указания трех позиций товара, которые должны быть добавлены в корзину вместе с прогнозируемыми товарами.</span><span class="sxs-lookup"><span data-stu-id="7dd58-166">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="7dd58-167">Столбец `[Model]` инструкции `SELECT` относится к столбцу, содержащемуся во вложенной таблице товаров.</span><span class="sxs-lookup"><span data-stu-id="7dd58-167">The `[Model]` column in the `SELECT` statement corresponds to the column in the nested products table.</span></span>  
  
     <span data-ttu-id="7dd58-168">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7dd58-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Modified Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="7dd58-169">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="7dd58-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="7dd58-170">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Modified Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="7dd58-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="7dd58-171">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="7dd58-171">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="7dd58-172">Запрос возвращает таблицу, содержащую три продукта: HL Mountain, бутылки воды и крыльев Set-Mountain.</span><span class="sxs-lookup"><span data-stu-id="7dd58-172">The query returns a table that contains three products: HL Mountain Tire, Water Bottle, and Fender Set - Mountain.</span></span> <span data-ttu-id="7dd58-173">В таблице эти продукты перечислены в порядке их вероятности.</span><span class="sxs-lookup"><span data-stu-id="7dd58-173">The table lists these products in order of probability.</span></span> <span data-ttu-id="7dd58-174">Продукт, который имеет наибольшую вероятность попасть в один и тот же список покупок с тремя продуктами, перечисленными в запросе, отображается в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="7dd58-174">The product that appears at the top of the table is the product that is most likely to be included in the same shopping cart as the three products specified in the query.</span></span> <span data-ttu-id="7dd58-175">Продукты, расположенные ниже, — следующие по вероятности включения в список покупок.</span><span class="sxs-lookup"><span data-stu-id="7dd58-175">The remaining products are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="7dd58-176">Кроме этого, в таблице содержатся статистические данные, описывающие точность прогноза.</span><span class="sxs-lookup"><span data-stu-id="7dd58-176">The table also contains statistics that describe the accuracy of the prediction.</span></span>  
  
     <span data-ttu-id="7dd58-177">В результатах этого запроса можно увидеть, что значение параметра *MINIMUM_PROBABILITY* влияет на результаты, возвращаемые запросом.</span><span class="sxs-lookup"><span data-stu-id="7dd58-177">You can see from the results of this query that the value of the *MINIMUM_PROBABILITY* parameter affects the results returned by the query.</span></span>  
  
 <span data-ttu-id="7dd58-178">Это было последним этапом учебника «Потребительская корзина».</span><span class="sxs-lookup"><span data-stu-id="7dd58-178">This is the last step in the Market Basket tutorial.</span></span> <span data-ttu-id="7dd58-179">Созданный набор моделей может быть использован для прогнозирования товаров, которые клиент обычно покупает одновременно.</span><span class="sxs-lookup"><span data-stu-id="7dd58-179">You now have a set of models that you can use to predict the products that customers might purchase at the same time.</span></span>  
  
 <span data-ttu-id="7dd58-180">Сведения об использовании расширений интеллектуального анализа данных в другом прогнозном сценарии см. в руководстве по использованию расширений интеллектуального анализа [данных Bike](../../2014/tutorials/bike-buyer-dmx-tutorial.md)Buyer.</span><span class="sxs-lookup"><span data-stu-id="7dd58-180">To learn how to use DMX in another predictive scenario, see [Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd58-181">См. также:</span><span class="sxs-lookup"><span data-stu-id="7dd58-181">See Also</span></span>  
 <span data-ttu-id="7dd58-182">[Примеры запросов к модели взаимосвязей](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="7dd58-182">[Association Model Query Examples](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span></span>  
 [<span data-ttu-id="7dd58-183">Интерфейсы запросов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7dd58-183">Data Mining Query Interfaces</span></span>](../../2014/analysis-services/data-mining/data-mining-query-tools.md)  
  
  
