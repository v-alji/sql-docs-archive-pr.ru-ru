---
title: Занятие 5. исполнение прогнозирующих запросов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0037bd2f-aa2d-464b-bf86-b0210f0438b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a5f4d6dd79f62541e207df688349f694680e2421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734693"
---
# <a name="lesson-5-executing-prediction-queries"></a><span data-ttu-id="68ea5-102">Занятие 5.: Выполнение запросов прогнозирования</span><span class="sxs-lookup"><span data-stu-id="68ea5-102">Lesson 5: Executing Prediction Queries</span></span>
  <span data-ttu-id="68ea5-103">На этом занятии для создания двух различных типов прогнозов на основе модели дерева принятия решений, созданной на [занятии 2](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md), будет использоваться форма [Выбор из \<model> прогнозирующего соединения (DMX)](/sql/dmx/select-from-model-cases-dmx) инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="68ea5-103">In this lesson, you will use the [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement to create two different types of predictions based on the decision tree model you created in [Lesson 2: Adding Mining Models to the Association Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="68ea5-104">Эти типы прогнозов определены ниже.</span><span class="sxs-lookup"><span data-stu-id="68ea5-104">These prediction types are defined below.</span></span>  
  
 <span data-ttu-id="68ea5-105">Одноэлементный запрос</span><span class="sxs-lookup"><span data-stu-id="68ea5-105">Singleton Query</span></span>  
 <span data-ttu-id="68ea5-106">Одноэлементный запрос используется для получения произвольно выбранных значений в процессе прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="68ea5-106">Use a singleton query to provide ad hoc values when making predictions.</span></span> <span data-ttu-id="68ea5-107">Например, можно определить, какова вероятность, что данный клиент купит велосипед. Для этого в запрос передаются такие величины, как расстояние от дома до работы покупателя, его почтовый индекс или, например, количество его детей.</span><span class="sxs-lookup"><span data-stu-id="68ea5-107">For example, you can determine whether a single customer is likely to be a bike buyer, by passing inputs to the query such as the commute distance, the area code, or the number of children of the customer.</span></span> <span data-ttu-id="68ea5-108">Одноэлементный запрос возвращает вероятность приобретения данным покупателем велосипеда, рассчитанную на основании введенных величин.</span><span class="sxs-lookup"><span data-stu-id="68ea5-108">The singleton query returns a value that indicates how likely the person is to purchase a bicycle based on those inputs.</span></span>  
  
 <span data-ttu-id="68ea5-109">Пакетный запрос</span><span class="sxs-lookup"><span data-stu-id="68ea5-109">Batch Query</span></span>  
 <span data-ttu-id="68ea5-110">Пакетный запрос используется для определения, кто из потенциальных клиентов, представленных в таблице, приобретет велосипед.</span><span class="sxs-lookup"><span data-stu-id="68ea5-110">Use a batch query to determine who in a table of potential customers is likely to purchase a bicycle.</span></span> <span data-ttu-id="68ea5-111">Например, если отдел маркетинга предоставит список клиентов и их атрибутов, то пакетный прогноз используется для предсказания, кто из клиентов, представленных в списке, с наибольшей вероятностью приобретет велосипед.</span><span class="sxs-lookup"><span data-stu-id="68ea5-111">For example, if your marketing department provides you with a list of customers and customer attributes, then you can use a batch prediction to determine who from the table is likely to purchase a bicycle.</span></span>  
  
 <span data-ttu-id="68ea5-112">В форме [Выбор из \<model> прогнозирующего объединения (DMX)](/sql/dmx/select-from-model-cases-dmx) инструкции SELECT содержатся три части:</span><span class="sxs-lookup"><span data-stu-id="68ea5-112">The [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement contains three parts:</span></span>  
  
-   <span data-ttu-id="68ea5-113">Список столбцов модели интеллектуального анализа данных и прогнозирующих функций, которые возвращаются в результатах.</span><span class="sxs-lookup"><span data-stu-id="68ea5-113">A list of the mining model columns and prediction functions that are returned in the results.</span></span> <span data-ttu-id="68ea5-114">Результаты также могут содержать входные столбцы источника данных.</span><span class="sxs-lookup"><span data-stu-id="68ea5-114">The results can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="68ea5-115">Запрос-источник, определяющий данные, которые используются при создании прогноза.</span><span class="sxs-lookup"><span data-stu-id="68ea5-115">The source query defining the data that is being used to create a prediction.</span></span> <span data-ttu-id="68ea5-116">Например, в пакетном запросе это может быть список клиентов.</span><span class="sxs-lookup"><span data-stu-id="68ea5-116">For example, in a batch query this could be a list of customers.</span></span>  
  
-   <span data-ttu-id="68ea5-117">Сопоставление столбцов модели интеллектуального анализа данных с исходными данными.</span><span class="sxs-lookup"><span data-stu-id="68ea5-117">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="68ea5-118">При совпадении этих имен можно использовать синтаксис NATURAL и пропустить процесс сопоставления столбцов.</span><span class="sxs-lookup"><span data-stu-id="68ea5-118">If these names match, then you can use NATURAL syntax and leave out the column mappings.</span></span>  
  
 <span data-ttu-id="68ea5-119">Запрос можно расширить функциями прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="68ea5-119">You can further enhance the query by using prediction functions.</span></span> <span data-ttu-id="68ea5-120">Функции прогнозирования предоставляют дополнительные сведения, например вероятность реализации прогноза, и обеспечивают поддержку прогноза в учебном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="68ea5-120">Prediction functions provide additional information, such as the probability of a prediction occurring, and provide support for the prediction in the training dataset.</span></span> <span data-ttu-id="68ea5-121">Дополнительные сведения о функциях прогнозирования см. в разделе [функции &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="68ea5-121">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="68ea5-122">Прогнозы в этом учебнике основаны на таблице ProspectiveBuyer из образца базы данных [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68ea5-122">The predictions in this tutorial are based on the ProspectiveBuyer table in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database.</span></span> <span data-ttu-id="68ea5-123">Таблица ProspectiveBuyer содержит список потенциальных клиентов и их характеристики.</span><span class="sxs-lookup"><span data-stu-id="68ea5-123">The ProspectiveBuyer table contains a list of potential customers and their associated characteristics.</span></span> <span data-ttu-id="68ea5-124">Клиенты, представленные в этой таблице, не зависят от клиентов, использовавшихся для создания дерева модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="68ea5-124">The customers in this table are independent of the customers that were used to create the decision tree mining model.</span></span>  
  
 <span data-ttu-id="68ea5-125">Прогнозы можно также создавать, используя построитель прогнозирующих запросов в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68ea5-125">You can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="68ea5-126">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="68ea5-126">Lesson Tasks</span></span>  
 <span data-ttu-id="68ea5-127">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="68ea5-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="68ea5-128">Создание одноэлементного запроса для определения вероятности покупки велосипеда конкретным клиентом.</span><span class="sxs-lookup"><span data-stu-id="68ea5-128">Create a singleton query to determine whether a specific customer is likely to purchase a bicycle.</span></span>  
  
-   <span data-ttu-id="68ea5-129">Пакетный запрос используется для определения того, кто из клиентов, представленных в таблице, приобретет велосипед.</span><span class="sxs-lookup"><span data-stu-id="68ea5-129">Create a batch query to determine which customers, listed in a table of customers, are likely to purchase a bicycle.</span></span>  
  
## <a name="singleton-query"></a><span data-ttu-id="68ea5-130">Одноэлементный запрос</span><span class="sxs-lookup"><span data-stu-id="68ea5-130">Singleton Query</span></span>  
 <span data-ttu-id="68ea5-131">Первым шагом является использование [модели выбор из &#60;&#62; прогнозируемого объединения &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) в одноэлементном прогнозирующим запросе.</span><span class="sxs-lookup"><span data-stu-id="68ea5-131">The first step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a singleton prediction query.</span></span> <span data-ttu-id="68ea5-132">В следующем фрагменте показан общий пример одноэлементной инструкции:</span><span class="sxs-lookup"><span data-stu-id="68ea5-132">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
```  
  
 <span data-ttu-id="68ea5-133">В первой строке кода определяются столбцы модели интеллектуального анализа данных, которые возвращает запрос, а также указывается имя модели интеллектуального анализа данных, которая использовалась для создания прогноза:</span><span class="sxs-lookup"><span data-stu-id="68ea5-133">The first line of the code defines the columns from the mining model that the query should return, and specifies the mining model that is used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
```  
  
 <span data-ttu-id="68ea5-134">В следующей строке определяются характеристики клиента, использованного в прогнозе:</span><span class="sxs-lookup"><span data-stu-id="68ea5-134">The next lines of the code define the characteristics of the customer that you use to create a prediction:</span></span>  
  
```  
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="68ea5-135">Если задана инструкция NATURAL PREDICTION JOIN, сервер сопоставляет каждый столбец из модели интеллектуального анализа данных входному столбцу по имени.</span><span class="sxs-lookup"><span data-stu-id="68ea5-135">If you specify NATURAL PREDICTION JOIN, the server matches each column from the model to a column from the input, based on column names.</span></span> <span data-ttu-id="68ea5-136">Если имена столбцов не совпадают, эти столбцы пропускаются.</span><span class="sxs-lookup"><span data-stu-id="68ea5-136">If column names do not match, the columns are ignored.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query"></a><span data-ttu-id="68ea5-137">Создание одноэлементного прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="68ea5-137">To create a singleton prediction query</span></span>  
  
1.  <span data-ttu-id="68ea5-138">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="68ea5-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="68ea5-139">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="68ea5-139">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="68ea5-140">Скопируйте общий пример одноэлементной инструкции в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="68ea5-140">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="68ea5-141">Вместо</span><span class="sxs-lookup"><span data-stu-id="68ea5-141">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="68ea5-142">на:</span><span class="sxs-lookup"><span data-stu-id="68ea5-142">with:</span></span>  
  
    ```  
    [Bike Buyer] AS Buyer, PredictHistogram([Bike Buyer]) AS Statistics  
    ```  
  
     <span data-ttu-id="68ea5-143">Инструкция AS используется для создания псевдонимов столбцов, которые возвращает запрос.</span><span class="sxs-lookup"><span data-stu-id="68ea5-143">The AS statement is used to alias columns returned by the query.</span></span> <span data-ttu-id="68ea5-144">Функция [PredictHistogram](/sql/dmx/predicthistogram-dmx) Возвращает статистические данные о прогнозе, включая вероятность и поддержку.</span><span class="sxs-lookup"><span data-stu-id="68ea5-144">The [PredictHistogram](/sql/dmx/predicthistogram-dmx) function returns statistics about the prediction, including the probability and the support.</span></span> <span data-ttu-id="68ea5-145">Дополнительные сведения о функциях, которые могут использоваться в операторе прогнозирования, см. в разделе [функции &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="68ea5-145">For more information about the functions that can be used in a prediction statement, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
4.  <span data-ttu-id="68ea5-146">Вместо</span><span class="sxs-lookup"><span data-stu-id="68ea5-146">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="68ea5-147">на:</span><span class="sxs-lookup"><span data-stu-id="68ea5-147">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="68ea5-148">Вместо</span><span class="sxs-lookup"><span data-stu-id="68ea5-148">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column name>], ...)  AS t  
    ```  
  
     <span data-ttu-id="68ea5-149">на:</span><span class="sxs-lookup"><span data-stu-id="68ea5-149">with:</span></span>  
  
    ```  
    (SELECT 35 AS [Age],  
      '5-10 Miles' AS [Commute Distance],  
      '1' AS [House Owner Flag],  
      2 AS [Number Cars Owned],  
      2 AS [Total Children]) AS t  
    ```  
  
     <span data-ttu-id="68ea5-150">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="68ea5-150">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
       [Bike Buyer] AS Buyer,  
       PredictHistogram([Bike Buyer]) AS Statistics  
    FROM  
       [Decision Tree]  
    NATURAL PREDICTION JOIN  
    (SELECT 35 AS [Age],  
       '5-10 Miles' AS [Commute Distance],  
       '1' AS [House Owner Flag],  
       2 AS [Number Cars Owned],  
       2 AS [Total Children]) AS t  
    ```  
  
6.  <span data-ttu-id="68ea5-151">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="68ea5-151">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="68ea5-152">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Singleton_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="68ea5-152">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_Query.dmx`.</span></span>  
  
8.  <span data-ttu-id="68ea5-153">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="68ea5-153">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="68ea5-154">Запрос возвращает прогноз, купит ли клиент с заданными характеристиками велосипед, а также статистические данные прогноза.</span><span class="sxs-lookup"><span data-stu-id="68ea5-154">The query returns a prediction about whether a customer with the specified characteristics will purchase a bicycle, as well as statistics about that prediction.</span></span>  
  
## <a name="batch-query"></a><span data-ttu-id="68ea5-155">Пакетный запрос</span><span class="sxs-lookup"><span data-stu-id="68ea5-155">Batch Query</span></span>  
 <span data-ttu-id="68ea5-156">Следующий шаг заключается в использовании [модели выбор из &#60;&#62; прогнозируемого объединения &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) в пакетном прогнозирующим запросе.</span><span class="sxs-lookup"><span data-stu-id="68ea5-156">The next step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a batch prediction query.</span></span> <span data-ttu-id="68ea5-157">Ниже представлен общий пример пакетной инструкции:</span><span class="sxs-lookup"><span data-stu-id="68ea5-157">The following is a generic example of a batch statement:</span></span>  
  
```  
SELECT TOP <number> <select list>   
FROM [<mining model name>]  
PREDICTION JOIN  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
ON <on clause, mapping,>  
WHERE <where clause, boolean expression,>  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="68ea5-158">Как и в одноэлементном запросе, первые две строки кода определяют столбцы из модели интеллектуального анализа, которые возвращает запрос, а также имя модели интеллектуального анализа данных, которая используется для создания прогноза.</span><span class="sxs-lookup"><span data-stu-id="68ea5-158">As in the singleton query, the first two lines of the code define the columns from mining model that the query returns, as well as the name of the mining model that is used to generate the prediction.</span></span> <span data-ttu-id="68ea5-159">Оператор TOP \<number> указывает, что запрос будет возвращать только число или результаты, заданные параметром \<number> .</span><span class="sxs-lookup"><span data-stu-id="68ea5-159">The TOP \<number> statement specifies that the query will only return the number or the results specified by \<number>.</span></span>  
  
 <span data-ttu-id="68ea5-160">Следующие строки кода определяют источник данных, на котором основан прогноз:</span><span class="sxs-lookup"><span data-stu-id="68ea5-160">The next lines of the code define the source data that the predictions are based on:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
```  
  
 <span data-ttu-id="68ea5-161">Имеется несколько вариантов метода получения исходных данных, но в этом учебнике используется инструкция OPENQUERY.</span><span class="sxs-lookup"><span data-stu-id="68ea5-161">You have several options for the method of retrieving the source data, but in this tutorial, you will use OPENQUERY.</span></span> <span data-ttu-id="68ea5-162">Дополнительные сведения о доступных параметрах см. в разделе [&#60;Source Data query&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="68ea5-162">For more information about the options available, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
 <span data-ttu-id="68ea5-163">В следующей строке определяется соответствие исходных столбцов в модели интеллектуального анализа данных столбцам исходных данных:</span><span class="sxs-lookup"><span data-stu-id="68ea5-163">The next line defines the mapping between the source columns in the mining model and the columns in the source data:</span></span>  
  
```  
ON <column mappings>  
```  
  
 <span data-ttu-id="68ea5-164">Предложение WHERE фильтрует результаты, возвращенные прогнозирующим запросом:</span><span class="sxs-lookup"><span data-stu-id="68ea5-164">The WHERE clause filters the results returned by the prediction query:</span></span>  
  
```  
WHERE <where clause, boolean expression,>  
```  
  
 <span data-ttu-id="68ea5-165">Последняя (необязательная) строка кода задает столбец, по которому упорядочиваются результаты:</span><span class="sxs-lookup"><span data-stu-id="68ea5-165">The last and optional line of the code specifies the column that the results will be ordered by:</span></span>  
  
```  
ORDER BY <expression> [DESC|ASC]  
```  
  
 <span data-ttu-id="68ea5-166">Используйте предложение ORDER BY в сочетании с \<number> оператором Top, чтобы отфильтровать возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="68ea5-166">Use ORDER BY in combination with the TOP \<number> statement, to filter the results that are returned.</span></span> <span data-ttu-id="68ea5-167">Например, в этом прогнозе возвращаются первые десять покупателей велосипедов, упорядоченных по степени вероятности реализации прогноза.</span><span class="sxs-lookup"><span data-stu-id="68ea5-167">For example, in this prediction you will return the top ten bike buyers, ordered by the probability of the prediction being correct.</span></span> <span data-ttu-id="68ea5-168">Для управления порядком вывода результатов можно использовать синтаксис [DESC|ASC].</span><span class="sxs-lookup"><span data-stu-id="68ea5-168">You can use [DESC|ASC] syntax to control the order in which the results are displayed.</span></span>  
  
#### <a name="to-create-a-batch-prediction-query"></a><span data-ttu-id="68ea5-169">Создание пакетного прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="68ea5-169">To create a batch prediction query</span></span>  
  
1.  <span data-ttu-id="68ea5-170">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="68ea5-170">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="68ea5-171">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="68ea5-171">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="68ea5-172">Скопируйте общий пример пакетной инструкции в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="68ea5-172">Copy the generic example of the batch statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="68ea5-173">Вместо</span><span class="sxs-lookup"><span data-stu-id="68ea5-173">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="68ea5-174">на:</span><span class="sxs-lookup"><span data-stu-id="68ea5-174">with:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    ```  
  
     <span data-ttu-id="68ea5-175">Предложение TOP 10 указывает, что запрос должен возвратить только десять первых результатов.</span><span class="sxs-lookup"><span data-stu-id="68ea5-175">The TOP 10 clause specifies that only the top ten results will be returned by the query.</span></span> <span data-ttu-id="68ea5-176">Инструкция ORDER BY в этом запросе упорядочивает результаты по степени вероятности прогноза, поэтому возвращаются только десять самых вероятных результатов.</span><span class="sxs-lookup"><span data-stu-id="68ea5-176">The ORDER BY statement in this query orders the results by the probability of the prediction being correct, so only the ten most likely results will be returned.</span></span>  
  
4.  <span data-ttu-id="68ea5-177">Вместо заполнителя:</span><span class="sxs-lookup"><span data-stu-id="68ea5-177">Replace the following placeholder:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="68ea5-178">используйте имя модели:</span><span class="sxs-lookup"><span data-stu-id="68ea5-178">With the name of the model:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="68ea5-179">Замените следующую универсальную инструкцию OPENQUERY:</span><span class="sxs-lookup"><span data-stu-id="68ea5-179">Replace the following generic OPENQUERY statement:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="68ea5-180">инструкцией, ссылающейся на текущее хранилище данных Adventureworks, например:</span><span class="sxs-lookup"><span data-stu-id="68ea5-180">With a statement that references the current Adventureworks data warehouse, such as:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2014],  
      'SELECT  
        [LastName],  
        [FirstName],  
        [MaritalStatus],  
        [Gender],  
        [YearlyIncome],  
        [TotalChildren],  
        [NumberChildrenAtHome],  
        [Education],  
        [Occupation],  
        [HouseOwnerFlag],  
        [NumberCarsOwned]  
      FROM  
        [dbo].[ProspectiveBuyer]  
      ') AS t  
    ```  
  
6.  <span data-ttu-id="68ea5-181">Замените следующий универсальный синтаксис:</span><span class="sxs-lookup"><span data-stu-id="68ea5-181">Replace the following generic syntax:</span></span>  
  
    ```  
    <ON clause, mapping,>   
    WHERE <where clause, boolean expression,>  
    ORDER BY <expression>  
    ```  
  
     <span data-ttu-id="68ea5-182">сопоставлением столбцов, которое требуется для этой модели и входного набора данных:</span><span class="sxs-lookup"><span data-stu-id="68ea5-182">With the column mappings needed for this model and input data set:</span></span>  
  
    ```  
    [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
     <span data-ttu-id="68ea5-183">Чтобы первыми вывести наиболее вероятные результаты, задайте `DESC`.</span><span class="sxs-lookup"><span data-stu-id="68ea5-183">Specify `DESC` in order to list the results with the highest probability first.</span></span>  
  
     <span data-ttu-id="68ea5-184">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="68ea5-184">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    FROM  
      [Decision Tree]  
    PREDICTION JOIN  
      OPENQUERY([Adventure Works DW 2014],  
        'SELECT  
          [LastName],  
          [FirstName],  
          [MaritalStatus],  
          [Gender],  
          [YearlyIncome],  
          [TotalChildren],  
          [NumberChildrenAtHome],  
          [Education],  
          [Occupation],  
          [HouseOwnerFlag],  
          [NumberCarsOwned]  
        FROM  
          [dbo].[ProspectiveBuyer]  
        ') AS t  
    ON  
      [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
7.  <span data-ttu-id="68ea5-185">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="68ea5-185">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="68ea5-186">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Batch_Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="68ea5-186">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Batch_Prediction.dmx`.</span></span>  
  
9. <span data-ttu-id="68ea5-187">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="68ea5-187">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="68ea5-188">Запрос возвращает таблицу с именами клиентов, прогноз о том, приобретет ли каждый клиент велосипед, и степень вероятности реализации прогноза.</span><span class="sxs-lookup"><span data-stu-id="68ea5-188">The query returns a table containing customer names, a prediction of whether each customer will purchase a bicycle, and the probability of the prediction.</span></span>  
  
 <span data-ttu-id="68ea5-189">Это последний шаг занятия «Покупатель велосипеда».</span><span class="sxs-lookup"><span data-stu-id="68ea5-189">This is the last step in the Bike Buyer tutorial.</span></span> <span data-ttu-id="68ea5-190">Теперь есть набор моделей интеллектуального анализа данных, которые можно использовать для изучения сходства клиентов и предсказания, будут ли потенциальные клиенты покупать велосипеды.</span><span class="sxs-lookup"><span data-stu-id="68ea5-190">You now have a set of mining models that you can use to explore similarities between you customers and predict whether potential customers will purchase a bicycle.</span></span>  
  
 <span data-ttu-id="68ea5-191">Сведения об использовании расширений интеллектуального анализа данных в сценарии потребительской корзины см. в разделе [учебник по DMX](../../2014/tutorials/market-basket-dmx-tutorial.md)для потребительской корзины.</span><span class="sxs-lookup"><span data-stu-id="68ea5-191">To learn how to use DMX in a Market Basket scenario, see [Market Basket DMX Tutorial](../../2014/tutorials/market-basket-dmx-tutorial.md).</span></span>  
  
  
