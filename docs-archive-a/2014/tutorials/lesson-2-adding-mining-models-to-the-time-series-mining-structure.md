---
title: Занятие 2. Добавление моделей интеллектуального анализа данных в структуру интеллектуального анализа временных рядов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75c2a74b-21ce-44fb-a26b-68be4c685c12
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ae0bb91fafb53c0c077a4e0d82558b550d0e6070
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654690"
---
# <a name="lesson-2-adding-mining-models-to-the-time-series-mining-structure"></a><span data-ttu-id="5805b-102">Урок 2. Добавление моделей в структуру интеллектуального анализа данных на основе временных рядов</span><span class="sxs-lookup"><span data-stu-id="5805b-102">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>
  <span data-ttu-id="5805b-103">На этом занятии будет добавлена новая модель интеллектуального анализа данных в структуру интеллектуального анализа данных, созданную на [занятии 1: создание модели и структуры интеллектуального анализа данных временных рядов](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="5805b-103">In this lesson, you will add a new mining model to the mining structure that you just created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="5805b-104">Инструкция ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="5805b-104">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="5805b-105">Чтобы добавить новую модель интеллектуального анализа данных к существующей структуре интеллектуального анализа данных, используется инструкция [ALTER MINING structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="5805b-105">In order to add a new mining model to an existing mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="5805b-106">Код инструкции можно разбить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="5805b-106">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="5805b-107">Определение структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5805b-107">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="5805b-108">Указание имени модели интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="5805b-108">Naming the mining model</span></span>  
  
-   <span data-ttu-id="5805b-109">Определение ключевого столбца</span><span class="sxs-lookup"><span data-stu-id="5805b-109">Defining the key column</span></span>  
  
-   <span data-ttu-id="5805b-110">Определение прогнозируемых столбцов</span><span class="sxs-lookup"><span data-stu-id="5805b-110">Defining the predictable columns</span></span>  
  
-   <span data-ttu-id="5805b-111">Задание алгоритма и изменений параметров</span><span class="sxs-lookup"><span data-stu-id="5805b-111">Specifying the algorithm and any parameter changes</span></span>  
  
 <span data-ttu-id="5805b-112">В следующем фрагменте показан общий пример инструкции ALTER MINING STRUCTURE.</span><span class="sxs-lookup"><span data-stu-id="5805b-112">The following is a generic example of the ALTER MINING STRUCTURE statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
   ([<key columns>],  
    <mining model columns>  
   )  
USING <algorithm name>([<algorithm parameters>])  
[WITH DRILLTHROUGH]  
```  
  
 <span data-ttu-id="5805b-113">В первой строке кода идентифицируется существующая структура интеллектуального анализа данных, к которой будут добавлены модели интеллектуального анализа данных:</span><span class="sxs-lookup"><span data-stu-id="5805b-113">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="5805b-114">В следующей строчке кода модели интеллектуального анализа данных, добавляемой к структуре интеллектуального анализа, присваивается имя:</span><span class="sxs-lookup"><span data-stu-id="5805b-114">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="5805b-115">Сведения об именовании объекта в расширениях интеллектуального анализа данных см. в разделе [идентификаторы &#40;&#41;расширений интеллектуального анализа данных ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="5805b-115">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="5805b-116">Следующие строки кода задают столбцы из структуры интеллектуального анализа, которые будут использоваться моделью интеллектуального анализа:</span><span class="sxs-lookup"><span data-stu-id="5805b-116">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key columns>],  
<mining model columns>  
```  
  
 <span data-ttu-id="5805b-117">Можно использовать только существующие столбцы структуры интеллектуального анализа, причем первый столбец из списка должен быть ключевым столбцом структуры интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="5805b-117">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="5805b-118">В следующих строках кода определяется алгоритм интеллектуального анализа, который создает модель интеллектуального анализа данных, и параметры, которые можно задать в алгоритме и указать, можно ли на основании модели интеллектуального анализа выполнять детализацию углублением подробных данных представления в обучающих вариантах.</span><span class="sxs-lookup"><span data-stu-id="5805b-118">The next lines of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm, and specify whether you can drill down from the mining model into view detailed data in the training cases:</span></span>  
  
```  
USING <algorithm name>([<algorithm parameters>])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="5805b-119">Дополнительные сведения о параметрах алгоритма, которые можно настроить, см. в [статье Технический справочник по алгоритму временных рядов (Майкрософт](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)).</span><span class="sxs-lookup"><span data-stu-id="5805b-119">For more information about the algorithm parameters that you can adjust, see [Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="5805b-120">С помощью следующего синтаксиса можно указать столбец модели интеллектуального анализа, который следует использовать для прогнозирования:</span><span class="sxs-lookup"><span data-stu-id="5805b-120">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="5805b-121">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="5805b-121">Lesson Tasks</span></span>  
 <span data-ttu-id="5805b-122">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="5805b-122">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="5805b-123">Добавление в структуру новой модели интеллектуального анализа временных рядов.</span><span class="sxs-lookup"><span data-stu-id="5805b-123">Add a new time series mining model to the structure.</span></span>  
  
-   <span data-ttu-id="5805b-124">Изменение параметров алгоритма для использования другого метода анализа и прогнозирования</span><span class="sxs-lookup"><span data-stu-id="5805b-124">Change the algorithm parameters to use a different method of analysis and prediction</span></span>  
  
## <a name="adding-an-arima-time-series-model-to-the-structure"></a><span data-ttu-id="5805b-125">Добавление в структуру модели временных рядов ARIMA</span><span class="sxs-lookup"><span data-stu-id="5805b-125">Adding an ARIMA Time Series Model to the Structure</span></span>  
 <span data-ttu-id="5805b-126">Первым шагом является добавление новой модели интеллектуального анализа прогнозирования в существующую структуру.</span><span class="sxs-lookup"><span data-stu-id="5805b-126">The first step is to add a new forecasting mining model to the existing structure.</span></span> <span data-ttu-id="5805b-127">По умолчанию алгоритм временных рядов ( [!INCLUDE[msCoName](../includes/msconame-md.md)] ) создает модели интеллектуального анализа данных с использованием двух алгоритмов: ARIMA и ARTxp, а также смешивает результаты.</span><span class="sxs-lookup"><span data-stu-id="5805b-127">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm creates time series mining models by using two algorithms, ARIMA and ARTXP, and blending the results.</span></span> <span data-ttu-id="5805b-128">Можно, однако, указать для использования один алгоритм, либо задать смешивание алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="5805b-128">However, you can specify a single algorithm to use, or you can specify the exact blend of algorithms.</span></span> <span data-ttu-id="5805b-129">На этом шаге добавляется новая модель, которая использует только алгоритм ARIMA.</span><span class="sxs-lookup"><span data-stu-id="5805b-129">In this step, you will add a new model that uses only the ARIMA algorithm.</span></span> <span data-ttu-id="5805b-130">Этот алгоритм оптимизирован для долгосрочного прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="5805b-130">This algorithm is optimized for long-term prediction.</span></span>  
  
#### <a name="to-add-an-arima-time-series-mining-model"></a><span data-ttu-id="5805b-131">Добавление модели интеллектуального анализа временных рядов ARIMA</span><span class="sxs-lookup"><span data-stu-id="5805b-131">To add an ARIMA time series mining model</span></span>  
  
1.  <span data-ttu-id="5805b-132">В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**, а затем выберите **расширения интеллектуального анализа данных** , чтобы открыть редактор запросов и новый пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="5805b-132">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="5805b-133">Скопируйте стандартный пример использования инструкции ALTER MINING STRUCTURE в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="5805b-133">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="5805b-134">Вместо</span><span class="sxs-lookup"><span data-stu-id="5805b-134">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="5805b-135">на:</span><span class="sxs-lookup"><span data-stu-id="5805b-135">with:</span></span>  
  
    ```  
    [Forecasting_MIXED_Structure]  
    ```  
  
4.  <span data-ttu-id="5805b-136">Вместо</span><span class="sxs-lookup"><span data-stu-id="5805b-136">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="5805b-137">на:</span><span class="sxs-lookup"><span data-stu-id="5805b-137">with:</span></span>  
  
    ```  
    Forecasting_ARIMA  
    ```  
  
5.  <span data-ttu-id="5805b-138">Вместо</span><span class="sxs-lookup"><span data-stu-id="5805b-138">Replace the following:</span></span>  
  
    ```  
    <key columns>,  
    ```  
  
     <span data-ttu-id="5805b-139">на:</span><span class="sxs-lookup"><span data-stu-id="5805b-139">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]  
    ```  
  
     <span data-ttu-id="5805b-140">Следует отметить, что не нужно повторять сведения для типа данных или содержимого, которые предоставлены в инструкции CREATE MINING MODEL, поскольку они уже сохранены в структуре интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="5805b-140">Note that you do not need to repeat any of the date type or content type information that you provided in the CREATE MINING MODEL statement, because this information is already stored in the mining structure.</span></span>  
  
6.  <span data-ttu-id="5805b-141">Вместо</span><span class="sxs-lookup"><span data-stu-id="5805b-141">Replace the following:</span></span>  
  
    ```  
    <mining model columns>  
    ```  
  
     <span data-ttu-id="5805b-142">на:</span><span class="sxs-lookup"><span data-stu-id="5805b-142">with:</span></span>  
  
    ```  
    ([Quantity] PREDICT,  
    [Amount] PREDICT  
    )  
    ```  
  
7.  <span data-ttu-id="5805b-143">Вместо</span><span class="sxs-lookup"><span data-stu-id="5805b-143">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([<algorithm parameters>])   
    [WITH DRILLTHROUGH]  
    ```  
  
     <span data-ttu-id="5805b-144">на:</span><span class="sxs-lookup"><span data-stu-id="5805b-144">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="5805b-145">В результате инструкция должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5805b-145">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARIMA]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
8.  <span data-ttu-id="5805b-146">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="5805b-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
9. <span data-ttu-id="5805b-147">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Forecasting_ARIMA.dmx` .</span><span class="sxs-lookup"><span data-stu-id="5805b-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARIMA.dmx`.</span></span>  
  
10. <span data-ttu-id="5805b-148">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="5805b-148">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-artxp-time-series-model-to-the-structure"></a><span data-ttu-id="5805b-149">Добавление в структуру модели временных рядов ARTXP</span><span class="sxs-lookup"><span data-stu-id="5805b-149">Adding an ARTXP Time Series Model to the Structure</span></span>  
 <span data-ttu-id="5805b-150">В SQL Server 2005 алгоритм ARTXP использовался по умолчанию и был оптимизирован для краткосрочного прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="5805b-150">The ARTXP algorithm was the default time series algorithm in SQL Server 2005 and is optimized for short-term prediction.</span></span> <span data-ttu-id="5805b-151">Для сравнения прогнозов, выполняемых тремя алгоритмами временных рядов, будет добавлена еще одна модель, основанная на алгоритме ARTXP.</span><span class="sxs-lookup"><span data-stu-id="5805b-151">To compare predictions by using all three time series algorithms, you will add one more model that is based on the ARTXP algorithm.</span></span>  
  
#### <a name="to-add-an-artxp-time-series-mining-model"></a><span data-ttu-id="5805b-152">Добавление модели интеллектуального анализа временных рядов ARTXP</span><span class="sxs-lookup"><span data-stu-id="5805b-152">To add an ARTXP time series mining model</span></span>  
  
1.  <span data-ttu-id="5805b-153">Скопируйте следующий код в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="5805b-153">Copy the following code into a blank query window.</span></span>  
  
     <span data-ttu-id="5805b-154">Следует отметить, что нет необходимости изменять что-либо, за исключением имени новой модели интеллектуального анализа и значения параметра FORECAST_METHOD.</span><span class="sxs-lookup"><span data-stu-id="5805b-154">Note that you do not need to change anything except the name of the new mining model, and the value of the FORECAST_METHOD parameter.</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARTXP]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARTXP')  
    WITH DRILLTHROUGH  
    ```  
  
2.  <span data-ttu-id="5805b-155">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="5805b-155">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
3.  <span data-ttu-id="5805b-156">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Forecasting_ARTXP.dmx` .</span><span class="sxs-lookup"><span data-stu-id="5805b-156">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARTXP.dmx`.</span></span>  
  
4.  <span data-ttu-id="5805b-157">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="5805b-157">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="5805b-158">На следующем занятии будет выполнена обработка всех моделей и структуры интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="5805b-158">In the next lesson, you will process all of the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="5805b-159">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="5805b-159">Next Lesson</span></span>  
 [<span data-ttu-id="5805b-160">Урок 3. Обработка структуры и моделей временных рядов</span><span class="sxs-lookup"><span data-stu-id="5805b-160">Lesson 3: Processing the Time Series Structure and Models</span></span>](../../2014/tutorials/lesson-3-processing-the-time-series-structure-and-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="5805b-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="5805b-161">See Also</span></span>  
 <span data-ttu-id="5805b-162">[Алгоритм временных рядов (Майкрософт)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="5805b-162">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 [<span data-ttu-id="5805b-163">Microsoft Time Series Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="5805b-163">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
