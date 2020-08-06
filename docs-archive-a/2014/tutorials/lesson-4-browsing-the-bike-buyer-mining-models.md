---
title: Занятие 4. Просмотр моделей интеллектуального анализа данных покупателя велосипеда | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8de3c500-f881-42da-a096-b6c03300d58d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 709df371d840d4b24e420b4fcd08750fd31e8075
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658593"
---
# <a name="lesson-4-browsing-the-bike-buyer-mining-models"></a><span data-ttu-id="51540-102">Занятие 4: Просмотр моделей интеллектуального анализа данных "Покупатель велосипеда"</span><span class="sxs-lookup"><span data-stu-id="51540-102">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>
  <span data-ttu-id="51540-103">На этом занятии будет использоваться инструкция [SELECT (расширения интеллектуального анализа данных)](/sql/dmx/select-dmx) для просмотра содержимого дерева принятия решений и кластеризации моделей интеллектуального анализа данных, созданных на [занятии 2. Добавление моделей интеллектуального анализа данных к структуре прогнозного интеллектуального анализа](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="51540-103">In this lesson, you will use the [SELECT (DMX)](/sql/dmx/select-dmx) statement to explore the content in the decision tree and clustering mining models that you created in [Lesson 2: Adding Mining Models to the Predictive Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="51540-104">Столбцы, содержащиеся в модели интеллектуального анализа данных, не являются столбцами, определенными структурой интеллектуального анализа данных, а являются особым набором столбцов, который описывает шаблоны и тренды, найденные алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="51540-104">The columns contained in a mining model are not the columns defined by the mining structure, but instead are a specific set of columns that describe the trends and patterns that are found by the algorithm.</span></span> <span data-ttu-id="51540-105">Эти столбцы модели интеллектуального анализа данных описаны в наборе строк схемы [набора строк DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) .</span><span class="sxs-lookup"><span data-stu-id="51540-105">These mining model columns are described in the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) schema rowset.</span></span> <span data-ttu-id="51540-106">Например, столбец MODEL_NAME в наборе строк схемы содержимого содержит имя модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-106">For example, the MODEL_NAME column in the content schema rowset contains the name of the mining model.</span></span> <span data-ttu-id="51540-107">Для кластерной модели интеллектуального анализа данных столбец NODE_CAPTION содержит имя каждого кластера, а столбец NODE_DESCRIPTION содержит описание характеристик каждого кластера.</span><span class="sxs-lookup"><span data-stu-id="51540-107">For a clustering mining model, the NODE_CAPTION column contains the name of each cluster, and the NODE_DESCRIPTION column contains a description of the characteristics of each cluster.</span></span> <span data-ttu-id="51540-108">Эти столбцы можно просмотреть с помощью команды выбрать из \<model> . CONTENT, инструкция расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-108">You can browse these columns by using the SELECT FROM \<model>.CONTENT statement in DMX.</span></span> <span data-ttu-id="51540-109">Эту инструкцию можно также использовать, чтобы исследовать данные, использованные для создания модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-109">You can also use this statement to explore the data that was used to create the mining model.</span></span> <span data-ttu-id="51540-110">Должна быть включена детализация структуры интеллектуального анализа данных, чтобы использовать эту инструкцию.</span><span class="sxs-lookup"><span data-stu-id="51540-110">Drillthrough must be enabled on the mining structure in order to use this statement.</span></span> <span data-ttu-id="51540-111">Дополнительные сведения об этой инструкции см. в разделе [Select from a &#60;model&#62;. СЛУЧАИ &#40;&#41;расширений интеллектуального анализа данных ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="51540-111">For more information about the statement, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
 <span data-ttu-id="51540-112">Также можно возвращать все состояния отдельного столбца при помощи инструкции SELECT DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="51540-112">You can also return all the states of a discrete column by using the SELECT DISTINCT statement.</span></span> <span data-ttu-id="51540-113">Например, при выполнении этой операции со столбцом «Пол» запрос вернет `male` и `female`.</span><span class="sxs-lookup"><span data-stu-id="51540-113">For example, if you perform this operation on a gender column, the query will return `male` and `female`.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="51540-114">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="51540-114">Lesson Tasks</span></span>  
 <span data-ttu-id="51540-115">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="51540-115">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="51540-116">Исследование содержимого моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51540-116">Explore the content contained within the mining models</span></span>  
  
-   <span data-ttu-id="51540-117">Возвращение из исходных данных случаев, которые использовались для обучения моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51540-117">Return the cases from the source data that was used to train the mining models</span></span>  
  
-   <span data-ttu-id="51540-118">Исследование различных состояний, доступных для отдельного столбца</span><span class="sxs-lookup"><span data-stu-id="51540-118">Explore the different states available for a specific discrete column</span></span>  
  
## <a name="returning-the-content-of-a-mining-model"></a><span data-ttu-id="51540-119">Возвращение содержимого модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51540-119">Returning the Content of a Mining Model</span></span>  
 <span data-ttu-id="51540-120">На этом занятии будет использоваться [&#62; модель выбор из &#60;. CONTENT &#40;инструкции DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) для возврата содержимого модели кластеризации.</span><span class="sxs-lookup"><span data-stu-id="51540-120">In this lesson, you use the [SELECT FROM &#60;model&#62;.CONTENT &#40;DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) statement to return the contents of the clustering model.</span></span>  
  
 <span data-ttu-id="51540-121">Ниже приведен общий пример ВЫБОРки из \<model> . Инструкция CONTENT:</span><span class="sxs-lookup"><span data-stu-id="51540-121">The following is a generic example of the SELECT FROM \<model>.CONTENT statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CONTENT  
WHERE <where clause>  
```  
  
 <span data-ttu-id="51540-122">В первой строке исходного кода определяются столбцы, возвращаемые из содержимого модели интеллектуального анализа данных, и модель интеллектуального анализа данных, с которой они связаны:</span><span class="sxs-lookup"><span data-stu-id="51540-122">The first line of the code defines the columns to return from the mining model content, and the mining model they are associated with:</span></span>  
  
```  
SELECT <select list> FROM [<mining model].CONTENT  
```  
  
 <span data-ttu-id="51540-123">Предложение .CONTENT рядом с именем модели интеллектуального анализа данных указывает на то, что вы возвращаете содержимое из модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-123">The .CONTENT clause next to the name of the mining model specifies that you are returning content from the mining model.</span></span> <span data-ttu-id="51540-124">Дополнительные сведения о столбцах, содержащихся в модели интеллектуального анализа данных, см. в разделе [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="51540-124">For more information about the columns contained in the mining model, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
 <span data-ttu-id="51540-125">При необходимости можно использовать последнюю строку, чтобы отфильтровать возвращаемый результат при помощи инструкции:</span><span class="sxs-lookup"><span data-stu-id="51540-125">You can optionally use the final line of the code to filter the results returned by the statement:</span></span>  
  
```  
WHERE <where clause>  
```  
  
 <span data-ttu-id="51540-126">Например, если нужно ограничить результаты запроса до тех кластеров, которые содержат большое количество случаев, можно добавить предложение WHERE в инструкцию SELECT:</span><span class="sxs-lookup"><span data-stu-id="51540-126">For example, if you want to restrict the results of the query to only the clusters that contain a high number of cases, you can add the following WHERE clause to the SELECT statement:</span></span>  
  
```  
WHERE NODE_SUPPORT > 100  
```  
  
 <span data-ttu-id="51540-127">Дополнительные сведения об использовании инструкции WHERE см. в разделе [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="51540-127">For more information about using the WHERE statement, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-content-of-the-clustering-mining-model"></a><span data-ttu-id="51540-128">Возврат содержимого кластерной модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51540-128">To return the content of the clustering mining model</span></span>  
  
1.  <span data-ttu-id="51540-129">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="51540-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="51540-130">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="51540-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="51540-131">Скопируйте общий пример ВЫБОРки из \<model> . Инструкция CONTENT в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="51540-131">Copy the generic example of the SELECT FROM \<model>.CONTENT statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="51540-132">Вместо</span><span class="sxs-lookup"><span data-stu-id="51540-132">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="51540-133">на:</span><span class="sxs-lookup"><span data-stu-id="51540-133">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="51540-134">Можно также заменить \* на список всех столбцов, содержащихся в [DMSCHEMA_MINING_MODEL_CONTENT наборе строк](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="51540-134">You can also replace \* with a list of any of the columns contained within the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
4.  <span data-ttu-id="51540-135">Вместо</span><span class="sxs-lookup"><span data-stu-id="51540-135">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="51540-136">на:</span><span class="sxs-lookup"><span data-stu-id="51540-136">with:</span></span>  
  
    ```  
    [Clustering]  
    ```  
  
     <span data-ttu-id="51540-137">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="51540-137">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT * FROM [Clustering].CONTENT  
    ```  
  
5.  <span data-ttu-id="51540-138">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="51540-138">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="51540-139">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `SELECT_CONTENT.dmx` .</span><span class="sxs-lookup"><span data-stu-id="51540-139">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_CONTENT.dmx`.</span></span>  
  
7.  <span data-ttu-id="51540-140">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="51540-140">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="51540-141">Запрос возвращает содержимое модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-141">The query returns the content of the mining model.</span></span>  
  
## <a name="use-drillthrough"></a><span data-ttu-id="51540-142">Использование детализации</span><span class="sxs-lookup"><span data-stu-id="51540-142">Use Drillthrough</span></span>  
 <span data-ttu-id="51540-143">Следующим шагом будет использование инструкции детализации для возвращения выборки ситуаций, использованных для обучения дерева решений модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-143">The next step is to use the drillthrough statement to return a sampling of the cases that were used to train the decision tree mining model.</span></span> <span data-ttu-id="51540-144">На этом занятии будет использоваться [&#62; модель выбор из &#60;. СЛУЧАИ &#40;инструкции DMX&#41;](/sql/dmx/select-from-model-content-dmx) для возврата содержимого модели дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="51540-144">In this lesson, you use the [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) statement to return the contents of the decision tree model.</span></span>  
  
 <span data-ttu-id="51540-145">Ниже приведен общий пример ВЫБОРки из \<model> . Оператор CASEs:</span><span class="sxs-lookup"><span data-stu-id="51540-145">The following is a generic example of the SELECT FROM \<model>.CASES statement:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model>].CASES  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="51540-146">В первой строке исходного кода определяются столбцы, возвращаемые из исходных данных, и модель интеллектуального анализа данных, в которой они хранятся:</span><span class="sxs-lookup"><span data-stu-id="51540-146">The first line of the code defines the columns to return from the source data, and the mining model they are contained within:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CASES  
```  
  
 <span data-ttu-id="51540-147">Предложение .CASES указывает на то, что выполняется запрос детализации.</span><span class="sxs-lookup"><span data-stu-id="51540-147">The .CASES clause specifies that you are performing a drillthrough query.</span></span> <span data-ttu-id="51540-148">Чтобы использовать детализацию, нужно включить ее при создании модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-148">In order to use drillthrough you must enable drillthrough when you create the mining model.</span></span>  
  
 <span data-ttu-id="51540-149">Последняя строка исходного кода является необязательной и указывает узел модели интеллектуального анализа данных, из которой извлекаются ситуации:</span><span class="sxs-lookup"><span data-stu-id="51540-149">The final line of the code is optional and specifies the node in the mining model that you are requesting cases from:</span></span>  
  
```  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="51540-150">Дополнительные сведения об использовании инструкции WHERE с IsInNode см. в разделе [Выбор из &#60;модели&#62;. СЛУЧАИ &#40;&#41;расширений интеллектуального анализа данных ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="51540-150">For more information about using the WHERE statement with IsInNode, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
#### <a name="to-return-the-cases-that-were-used-to-train-the-mining-model"></a><span data-ttu-id="51540-151">Возврат ситуаций, использованных для обучения модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51540-151">To return the cases that were used to train the mining model</span></span>  
  
1.  <span data-ttu-id="51540-152">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="51540-152">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="51540-153">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="51540-153">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="51540-154">Скопируйте общий пример ВЫБОРки из \<model> . CASEs в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="51540-154">Copy the generic example of the SELECT FROM \<model>.CASES statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="51540-155">Вместо</span><span class="sxs-lookup"><span data-stu-id="51540-155">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="51540-156">на:</span><span class="sxs-lookup"><span data-stu-id="51540-156">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="51540-157">Также можно заменить символ «\*» на список любых столбцов исходных данных (например [Bike Buyer]).</span><span class="sxs-lookup"><span data-stu-id="51540-157">You can also replace \* with a list of any of the columns contained within the source data (such as [Bike Buyer]).</span></span>  
  
4.  <span data-ttu-id="51540-158">Вместо</span><span class="sxs-lookup"><span data-stu-id="51540-158">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="51540-159">на:</span><span class="sxs-lookup"><span data-stu-id="51540-159">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="51540-160">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="51540-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT *   
    FROM [Decision Tree].CASES  
    ```  
  
5.  <span data-ttu-id="51540-161">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="51540-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="51540-162">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `SELECT_DRILLTHROUGH.dmx` .</span><span class="sxs-lookup"><span data-stu-id="51540-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DRILLTHROUGH.dmx`.</span></span>  
  
7.  <span data-ttu-id="51540-163">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="51540-163">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="51540-164">Запрос возвращает исходные данные, использованные для обучения дерева решений модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-164">The query returns the source data that was used to train the decision tree mining model.</span></span>  
  
## <a name="return-the-states-of-a-discrete-mining-model-column"></a><span data-ttu-id="51540-165">Возвращение состояний отдельного столбца модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="51540-165">Return the States of a Discrete Mining Model Column</span></span>  
 <span data-ttu-id="51540-166">Следующим шагом будет использование инструкции SELECT DISTINCT для возвращения различных доступных состояний в указанном столбце модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-166">The next step is to use the SELECT DISTINCT statement to return the different possible states in the specified mining model column.</span></span>  
  
 <span data-ttu-id="51540-167">Ниже следует базовый пример инструкции SELECT DISTINCT:</span><span class="sxs-lookup"><span data-stu-id="51540-167">The following is a generic example of the SELECT DISTINCT statement:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
FROM [<mining model>]  
```  
  
 <span data-ttu-id="51540-168">Первая строка исходного кода определяет столбцы модели интеллектуального анализа данных, для которых возвращаются состояния:</span><span class="sxs-lookup"><span data-stu-id="51540-168">The first line of the code defines the mining model columns for which the states are returned:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
```  
  
 <span data-ttu-id="51540-169">Необходимо включить DISTINCT, чтобы вернуть все состояния столбца.</span><span class="sxs-lookup"><span data-stu-id="51540-169">You must include DISTINCT in order to return all of the states of the column.</span></span> <span data-ttu-id="51540-170">Если не включить DISTINCT, полная инструкция становится ярлыком для прогноза и, скорее всего, возвращает состояние указанного столбца.</span><span class="sxs-lookup"><span data-stu-id="51540-170">If you exclude DISTINCT, then the full statement becomes a shortcut for a prediction and returns the most likely state of the specified column.</span></span> <span data-ttu-id="51540-171">Дополнительные сведения см. в разделе [SELECT (расширения интеллектуального анализа данных)](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="51540-171">For more information, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-states-of-a-discrete-column"></a><span data-ttu-id="51540-172">Возврат состояний отдельного столбца</span><span class="sxs-lookup"><span data-stu-id="51540-172">To return the states of a discrete column</span></span>  
  
1.  <span data-ttu-id="51540-173">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="51540-173">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="51540-174">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="51540-174">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="51540-175">Скопируйте базовый пример инструкции SELECT Distinct в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="51540-175">Copy the generic example of the SELECT Distinct statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="51540-176">Вместо</span><span class="sxs-lookup"><span data-stu-id="51540-176">Replace the following:</span></span>  
  
    ```  
    [<column,name>   
    ```  
  
     <span data-ttu-id="51540-177">на:</span><span class="sxs-lookup"><span data-stu-id="51540-177">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="51540-178">Вместо</span><span class="sxs-lookup"><span data-stu-id="51540-178">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="51540-179">на:</span><span class="sxs-lookup"><span data-stu-id="51540-179">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="51540-180">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="51540-180">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT DISTINCT [Bike Buyer]   
    FROM [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="51540-181">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="51540-181">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="51540-182">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `SELECT_DISCRETE.dmx` .</span><span class="sxs-lookup"><span data-stu-id="51540-182">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DISCRETE.dmx`.</span></span>  
  
7.  <span data-ttu-id="51540-183">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="51540-183">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="51540-184">Запрос возвращает возможные состояния столбца Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="51540-184">The query returns the possible states of the Bike Buyer column.</span></span>  
  
 <span data-ttu-id="51540-185">На следующем занятии вы спрогнозируете, будут ли потенциальные клиенты покупать велосипеды, используя дерево решений модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="51540-185">In the next lesson, you will predict whether potential customers will be bike buyers by using the decision tree mining model.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="51540-186">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="51540-186">Next Lesson</span></span>  
 [<span data-ttu-id="51540-187">Занятие 5.: Выполнение запросов прогнозирования</span><span class="sxs-lookup"><span data-stu-id="51540-187">Lesson 5: Executing Prediction Queries</span></span>](../../2014/tutorials/lesson-5-executing-prediction-queries.md)  
  
  
