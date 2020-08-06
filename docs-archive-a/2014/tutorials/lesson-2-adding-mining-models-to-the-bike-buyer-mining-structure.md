---
title: 'Занятие 2: Добавление моделей интеллектуального анализа данных в структуру интеллектуального анализа данных покупателя велосипеда | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 03fe44c5-6452-4ed0-95f6-9682670c0f52
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: de65fb7a85154f607cd8f266faec4621cdc41476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733381"
---
# <a name="lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure"></a><span data-ttu-id="5a7f1-102">Урок 2. Добавление моделей к структуре интеллектуального анализа данных "Покупатель велосипеда"</span><span class="sxs-lookup"><span data-stu-id="5a7f1-102">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="5a7f1-103">На этом занятии вы добавите две модели интеллектуального анализа данных в структуру интеллектуального анализа данных Bike Buyer, созданную на [занятии 1: создание структуры интеллектуального анализа данных покупателя велосипеда](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="5a7f1-103">In this lesson, you will add two mining models to the Bike Buyer mining structure that you created [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span></span> <span data-ttu-id="5a7f1-104">Эти модели интеллектуального анализа позволяют просматривать данные, используя одну модель, и создавать прогнозы с помощью другой модели.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-104">These mining models will allow you to explore the data using one model, and to create predictions using another.</span></span>  
  
 <span data-ttu-id="5a7f1-105">Чтобы узнать, как потенциальные клиенты могут классифицироваться по их характеристикам, необходимо создать модель интеллектуального анализа данных на основе [алгоритма кластеризации (Майкрософт](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)).</span><span class="sxs-lookup"><span data-stu-id="5a7f1-105">To explore how potential customers can be categorized by their characteristics, you will create a mining model based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span> <span data-ttu-id="5a7f1-106">На одном из следующих занятий будет изучено, каким образом этот алгоритм находит кластеры заказчиков с похожими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-106">In a later lesson, you will explore how this algorithm finds clusters of customers who share similar characteristics.</span></span> <span data-ttu-id="5a7f1-107">Например, может оказаться, что некоторые заказчики живут близко друг от друга, ездят на велосипеде и имеют примерно равный уровень образования.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-107">For example, you might find that certain customers tend to live close to each other, commute by bicycle, and have similar education backgrounds.</span></span> <span data-ttu-id="5a7f1-108">Можно использовать данные кластеры, чтобы лучше понять, каким образом различные заказчики связаны между собой, и использовать эти сведения для создания маркетинговой стратегии, рассчитанной на конкретных заказчиков.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-108">You can use these clusters to better understand how different customers are related, and to use the information to create a marketing strategy that targets specific customers.</span></span>  
  
 <span data-ttu-id="5a7f1-109">Чтобы предсказать, может ли потенциальный клиент приобрести велосипед, вы создадите модель интеллектуального анализа данных на основе [алгоритма дерева принятия решений (Майкрософт](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)).</span><span class="sxs-lookup"><span data-stu-id="5a7f1-109">To predict whether a potential customer is likely to buy a bicycle, you will create a mining model based on the [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="5a7f1-110">Этот алгоритм просматривает данные, связанные с каждым потенциальным заказчиком, и находит характеристики, релевантные для прогнозирования покупки велосипеда.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-110">This algorithm looks through the information that is associated with each potential customer, and finds characteristics that are useful in predicting if they will buy a bicycle.</span></span> <span data-ttu-id="5a7f1-111">Затем он сравнивает значения характеристик заказчиков, уже купивших велосипеды, с характеристиками потенциальных заказчиков для определения возможности того, что они купят велосипеды.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-111">It then compares the values of the characteristics of previous bike buyers against new potential customers to determine whether the new potential customers are likely to buy a bicycle.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="5a7f1-112">Инструкция ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="5a7f1-112">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="5a7f1-113">Чтобы добавить модель интеллектуального анализа данных к структуре интеллектуального анализа данных, используется инструкция [ALTER MINING structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="5a7f1-113">In order to add a mining model to the mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="5a7f1-114">Код инструкции можно разбить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-114">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="5a7f1-115">Определение структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5a7f1-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="5a7f1-116">Указание имени модели интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="5a7f1-116">Naming the mining model</span></span>  
  
-   <span data-ttu-id="5a7f1-117">Определение ключевого столбца</span><span class="sxs-lookup"><span data-stu-id="5a7f1-117">Defining the key column</span></span>  
  
-   <span data-ttu-id="5a7f1-118">Определение столбцов исходных данных и прогнозируемых столбцов</span><span class="sxs-lookup"><span data-stu-id="5a7f1-118">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="5a7f1-119">Идентификация алгоритма и изменений параметра</span><span class="sxs-lookup"><span data-stu-id="5a7f1-119">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="5a7f1-120">В следующем фрагменте показан стандартный пример инструкции ALTER MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-120">The following is a generic example of the ALTER MINING MODEL statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
(  
    [<key column>],  
    <mining model columns>,  
) USING <algorithm name>( <algorithm parameters> )  
WITH FILTER (<expression>)  
```  
  
 <span data-ttu-id="5a7f1-121">В первой строке кода идентифицируется существующая структура интеллектуального анализа данных, к которой будут добавлены модели интеллектуального анализа данных:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-121">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="5a7f1-122">В следующей строчке кода модели интеллектуального анализа данных, добавляемой к структуре интеллектуального анализа, присваивается имя:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-122">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="5a7f1-123">Сведения об именовании объекта в расширениях интеллектуального анализа данных см. в разделе [идентификаторы &#40;&#41;расширений интеллектуального анализа данных ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="5a7f1-123">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="5a7f1-124">Следующие строки кода задают столбцы из структуры интеллектуального анализа, которые будут использоваться моделью интеллектуального анализа:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-124">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns>  
```  
  
 <span data-ttu-id="5a7f1-125">Можно использовать только существующие столбцы структуры интеллектуального анализа, причем первый столбец из списка должен быть ключевым столбцом структуры интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-125">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="5a7f1-126">В последней строчке кода определяется алгоритм интеллектуального анализа данных, который создает модель интеллектуального анализа, и параметры, которые можно передать алгоритму:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-126">The next line of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm:</span></span>  
  
```  
) USING <algorithm name>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="5a7f1-127">Дополнительные сведения о параметрах алгоритма, которые можно настроить, см. в разделе [алгоритм дерева принятия решений (Майкрософт](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) ) и [алгоритм кластеризации (Майкрософт](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)).</span><span class="sxs-lookup"><span data-stu-id="5a7f1-127">For more information about the algorithm parameters that you can adjust, see [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) and [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span>  
  
 <span data-ttu-id="5a7f1-128">С помощью следующего синтаксиса можно указать столбец модели интеллектуального анализа, который следует использовать для прогнозирования:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-128">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
 <span data-ttu-id="5a7f1-129">В последней строке кода, которая является необязательной, определяется фильтр, применяемый при обучении и проверке модели.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-129">The final line of the code, which is optional, defines a filter that is applied when training and testing the model.</span></span> <span data-ttu-id="5a7f1-130">Дополнительные сведения о применении фильтров к моделям интеллектуального анализа данных см. в разделе [Filters for Mining models &#40;Analysis Services-data mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="5a7f1-130">For more information about how to apply filters to mining models, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="5a7f1-131">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="5a7f1-131">Lesson Tasks</span></span>  
 <span data-ttu-id="5a7f1-132">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-132">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="5a7f1-133">Добавление модели интеллектуального анализа данных дерева принятия решений в структуру Bike Buyer с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="5a7f1-133">Add a decision tree mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm</span></span>  
  
-   <span data-ttu-id="5a7f1-134">Добавление модели интеллектуального анализа данных кластеризации в структуру закупщика велосипедов с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма кластеризации</span><span class="sxs-lookup"><span data-stu-id="5a7f1-134">Add a clustering mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm</span></span>  
  
-   <span data-ttu-id="5a7f1-135">Поскольку требуется ознакомиться с результатами для всех вариантов, ни для одной модели не должен быть добавлен фильтр.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-135">Because you want to see results for all cases, you will not yet add a filter to either model.</span></span>  
  
## <a name="adding-a-decision-tree-mining-model-to-the-structure"></a><span data-ttu-id="5a7f1-136">Добавление модели интеллектуального анализа дерева принятия решений к структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5a7f1-136">Adding a Decision Tree Mining Model to the Structure</span></span>  
 <span data-ttu-id="5a7f1-137">Первым шагом является добавление модели интеллектуального анализа данных на основе [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-137">The first step is to add a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
#### <a name="to-add-a-decision-tree-mining-model"></a><span data-ttu-id="5a7f1-138">Для добавления модели интеллектуального анализа дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="5a7f1-138">To add a decision tree mining model</span></span>  
  
1.  <span data-ttu-id="5a7f1-139">В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**, а затем выберите **расширения интеллектуального анализа данных** , чтобы открыть редактор запросов и новый пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-139">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="5a7f1-140">Скопируйте стандартный пример использования инструкции ALTER MINING STRUCTURE в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-140">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="5a7f1-141">Вместо</span><span class="sxs-lookup"><span data-stu-id="5a7f1-141">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="5a7f1-142">на:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-142">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="5a7f1-143">Вместо</span><span class="sxs-lookup"><span data-stu-id="5a7f1-143">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="5a7f1-144">на:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-144">with:</span></span>  
  
    ```  
    Decision Tree  
    ```  
  
5.  <span data-ttu-id="5a7f1-145">Вместо</span><span class="sxs-lookup"><span data-stu-id="5a7f1-145">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    ```  
  
     <span data-ttu-id="5a7f1-146">на:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-146">with:</span></span>  
  
    ```  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ```  
  
     <span data-ttu-id="5a7f1-147">В этом случае столбец `[Bike Buyer]` обозначается как столбец PREDICT.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-147">In this case, the `[Bike Buyer]` column has been designated as the PREDICT column.</span></span>  
  
6.  <span data-ttu-id="5a7f1-148">Вместо</span><span class="sxs-lookup"><span data-stu-id="5a7f1-148">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )   
    ```  
  
     <span data-ttu-id="5a7f1-149">на:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-149">with:</span></span>  
  
    ```  
    Using Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="5a7f1-150">Инструкция WITH DRILLTHROUGH позволяет просматривать объекты, использованные для построения модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-150">The WITH DRILLTHROUGH statement allows you to explore the cases that were used to build the mining model.</span></span>  
  
     <span data-ttu-id="5a7f1-151">В результате инструкция должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-151">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Decision Tree]  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ) USING Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
7.  <span data-ttu-id="5a7f1-152">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="5a7f1-153">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `DT_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="5a7f1-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `DT_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="5a7f1-154">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="5a7f1-154">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-a-clustering-mining-model-to-the-structure"></a><span data-ttu-id="5a7f1-155">Добавление модели интеллектуального анализа кластеризации к структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5a7f1-155">Adding a Clustering Mining Model to the Structure</span></span>  
 <span data-ttu-id="5a7f1-156">Теперь вы можете добавить модель интеллектуального анализа данных в структуру интеллектуального анализа данных покупателя велосипеда на основе [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма кластеризации.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-156">You can now add a mining model to the Bike Buyer mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span> <span data-ttu-id="5a7f1-157">Поскольку модель интеллектуального анализа данных кластеризации будет использовать все столбцы, определенные в структуре интеллектуального анализа данных, можно использовать контекстное меню, чтобы добавить модель к структуре без определения столбцов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-157">Because the clustering mining model will use all the columns defined in the mining structure, you can use a shortcut to add the model to the structure by omitting the definition of the mining columns.</span></span>  
  
#### <a name="to-add-a-clustering-mining-model"></a><span data-ttu-id="5a7f1-158">Добавление модели интеллектуального анализа кластеризации</span><span class="sxs-lookup"><span data-stu-id="5a7f1-158">To add a Clustering mining model</span></span>  
  
1.  <span data-ttu-id="5a7f1-159">В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**, а затем выберите **расширения интеллектуального анализа данных** , чтобы открыть редактор запросов, и новый пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-159">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor opens and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="5a7f1-160">Скопируйте стандартный пример использования инструкции ALTER MINING STRUCTURE в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-160">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="5a7f1-161">Вместо</span><span class="sxs-lookup"><span data-stu-id="5a7f1-161">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="5a7f1-162">на:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-162">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="5a7f1-163">Вместо</span><span class="sxs-lookup"><span data-stu-id="5a7f1-163">Replace the following:</span></span>  
  
    ```  
    <mining model>   
    ```  
  
     <span data-ttu-id="5a7f1-164">на:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-164">with:</span></span>  
  
    ```  
    Clustering Model  
    ```  
  
5.  <span data-ttu-id="5a7f1-165">Удалите:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-165">Delete the following:</span></span>  
  
    ```  
    (  
        [<key column>],  
        <mining model columns>,  
    )  
    ```  
  
6.  <span data-ttu-id="5a7f1-166">Вместо</span><span class="sxs-lookup"><span data-stu-id="5a7f1-166">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="5a7f1-167">на:</span><span class="sxs-lookup"><span data-stu-id="5a7f1-167">with:</span></span>  
  
    ```  
    USING Microsoft_Clustering  
    ```  
  
     <span data-ttu-id="5a7f1-168">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Clustering]  
    USING Microsoft_Clustering   
    ```  
  
7.  <span data-ttu-id="5a7f1-169">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="5a7f1-170">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Clustering_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="5a7f1-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Clustering_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="5a7f1-171">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="5a7f1-171">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="5a7f1-172">На следующем занятии вы научитесь обрабатывать модели и структуры интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="5a7f1-172">In the next lesson, you will process the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="5a7f1-173">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="5a7f1-173">Next Lesson</span></span>  
 [<span data-ttu-id="5a7f1-174">Урок 3. Обработка структуры интеллектуального анализа данных "Покупатель велосипеда"</span><span class="sxs-lookup"><span data-stu-id="5a7f1-174">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-bike-buyer-mining-structure.md)  
  
  
