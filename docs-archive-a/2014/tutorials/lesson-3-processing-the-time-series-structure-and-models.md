---
title: Занятие 3. Обработка структуры и моделей временных рядов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 16e27b57-eae1-47a7-a02c-47b6ed487d87
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 493d27c9836eb765c655eba5bbb004e4d48cde40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733369"
---
# <a name="lesson-3-processing-the-time-series-structure-and-models"></a><span data-ttu-id="6eced-102">Урок 3. Обработка структуры и моделей временных рядов</span><span class="sxs-lookup"><span data-stu-id="6eced-102">Lesson 3: Processing the Time Series Structure and Models</span></span>
  <span data-ttu-id="6eced-103">На этом занятии для обработки созданных структур интеллектуального анализа данных и моделей интеллектуального анализа данных с использованием временных рядов используется инструкция [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="6eced-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement to process the time series mining structures and mining models that you created.</span></span>  
  
 <span data-ttu-id="6eced-104">При обработке структуры интеллектуального анализа данных службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] считывают исходные данные и создают структуры, поддерживающие модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="6eced-105">Всегда необходимо выполнять обработку модели интеллектуального анализа данных и структуры при первом создании.</span><span class="sxs-lookup"><span data-stu-id="6eced-105">You always have to process a mining model and structure when you first create it.</span></span> <span data-ttu-id="6eced-106">Если задана структура интеллектуального анализа данных при использовании инструкции INSERT INTO, инструкция обрабатывает эту структуру и все связанные с ней модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-106">If you specify the mining structure when using INSERT INTO, the statement processes the mining structure and all its associated mining models.</span></span>  
  
 <span data-ttu-id="6eced-107">При добавлении модели интеллектуального анализа данных к уже обработанной структуре интеллектуального анализа данных можно использовать инструкцию `INSERT INTO MINING MODEL` для обработки новой модели интеллектуального анализа данных с помощью существующих данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-107">When you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to process just the new mining model by using the existing data.</span></span>  
  
 <span data-ttu-id="6eced-108">Дополнительные сведения об обработке моделей интеллектуального анализа данных см. в разделе [требования к обработке и рекомендации &#40;&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6eced-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="6eced-109">Инструкция INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="6eced-109">INSERT INTO Statement</span></span>  
 <span data-ttu-id="6eced-110">Чтобы обучить структуру интеллектуального анализа данных временных рядов и все связанные с ней модели интеллектуального анализа данных, используйте инструкцию [INSERT в &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="6eced-110">In order to train the time series mining structure and all its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="6eced-111">Код инструкции можно разбить на следующие части.</span><span class="sxs-lookup"><span data-stu-id="6eced-111">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="6eced-112">Определение структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="6eced-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="6eced-113">Список столбцов структуры интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="6eced-113">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="6eced-114">Определение обучающих данных</span><span class="sxs-lookup"><span data-stu-id="6eced-114">Defining the training data</span></span>  
  
 <span data-ttu-id="6eced-115">Далее приведен общий пример инструкции `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="6eced-115">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="6eced-116">В первой строчке кода задается структура интеллектуального анализа данных, которую необходимо обучить:</span><span class="sxs-lookup"><span data-stu-id="6eced-116">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="6eced-117">Следующие строки кода указывают столбцы, определенные структурой интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-117">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="6eced-118">Необходимо перечислить все столбцы структуры интеллектуального анализа данных, и каждый столбец должен сопоставляться с каким-либо столбцом из данных исходного запроса.</span><span class="sxs-lookup"><span data-stu-id="6eced-118">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="6eced-119">Последние строки кода определяют данные, которые будут использованы для обучения структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-119">The final lines of the code define the data that will be used to train the mining structure.</span></span>  
  
```  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="6eced-120">На этом занятии требуется определить исходные данные с помощью инструкции `OPENQUERY`.</span><span class="sxs-lookup"><span data-stu-id="6eced-120">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="6eced-121">Дополнительные сведения о других методах определения запроса к исходным данным см. в разделе [&#60;Source Data query&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="6eced-121">For more information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="6eced-122">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="6eced-122">Lesson Tasks</span></span>  
 <span data-ttu-id="6eced-123">На этом занятии требуется выполнить следующую задачу:</span><span class="sxs-lookup"><span data-stu-id="6eced-123">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="6eced-124">обработать структуру интеллектуального анализа данных Forecasting_MIXED_Structure;</span><span class="sxs-lookup"><span data-stu-id="6eced-124">Process the mining structure Forecasting_MIXED_Structure</span></span>  
  
-   <span data-ttu-id="6eced-125">обработать связанные модели интеллектуального анализа данных Forecasting_MIXED, Forecasting_ARIMA и Forecasting_ARTXP.</span><span class="sxs-lookup"><span data-stu-id="6eced-125">Process the related mining models Forecasting_MIXED, Forecasting_ARIMA, and Forecasting_ARTXP</span></span>  
  
## <a name="processing-the-time-series-mining-structure"></a><span data-ttu-id="6eced-126">Обработка структуры интеллектуального анализа данных временных рядов</span><span class="sxs-lookup"><span data-stu-id="6eced-126">Processing the Time Series Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-and-related-mining-models-by-using-insert-into"></a><span data-ttu-id="6eced-127">Обработка структуры интеллектуального анализа данных и связанных с ней моделей с помощью инструкции INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="6eced-127">To process the mining structure and related mining models by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="6eced-128">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="6eced-128">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="6eced-129">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="6eced-129">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="6eced-130">Скопируйте стандартный пример использования инструкции INSERT INTO в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="6eced-130">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="6eced-131">Вместо</span><span class="sxs-lookup"><span data-stu-id="6eced-131">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="6eced-132">на:</span><span class="sxs-lookup"><span data-stu-id="6eced-132">with:</span></span>  
  
    ```  
    Forecasting_MIXED_Structure  
    ```  
  
4.  <span data-ttu-id="6eced-133">Вместо</span><span class="sxs-lookup"><span data-stu-id="6eced-133">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="6eced-134">на:</span><span class="sxs-lookup"><span data-stu-id="6eced-134">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]   
    ```  
  
5.  <span data-ttu-id="6eced-135">Вместо</span><span class="sxs-lookup"><span data-stu-id="6eced-135">Replace the following:</span></span>  
  
    ```  
    OPENQUERY(<source data definition>)  
    ```  
  
     <span data-ttu-id="6eced-136">на:</span><span class="sxs-lookup"><span data-stu-id="6eced-136">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2008R2],'SELECT [ReportingDate], [ModelRegion], [Quantity], [Amount]  
    FROM vTimeSeries ORDER BY [ReportingDate]')  
    ```  
  
     <span data-ttu-id="6eced-137">Исходный запрос ссылается на [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] источник данных, определенный в образце проекта интермедиатетуториал.</span><span class="sxs-lookup"><span data-stu-id="6eced-137">The source query references the  [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the IntermediateTutorial sample project.</span></span> <span data-ttu-id="6eced-138">Этот источник данных используется запросом для доступа к представлению vTimeSeries.</span><span class="sxs-lookup"><span data-stu-id="6eced-138">It uses this data source to access the view vTimeSeries.</span></span> <span data-ttu-id="6eced-139">Это представление содержит исходные данные, которые будут использованы для обучения модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-139">This view contains the source data that will be used to train the mining model.</span></span> <span data-ttu-id="6eced-140">Если вы не знакомы с этим проектом или представлениями, см. раздел[занятие 2. Создание сценария прогнозирования &#40;руководстве по интеллектуальному анализу данных&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="6eced-140">If you are not familiar with this project or this views, see[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="6eced-141">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6eced-141">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Forecasting_MIXED_Structure]  
    (  
       [ReportingDate],[ModelRegion],[Quantity],[Amount])  
    )  
    OPENQUERY(  
    [Adventure Works DW 2008R2],  
    'SELECT [ReportingDate],[ModelRegion],[Quantity],[Amount] FROM vTimeSeries ORDER BY [ReportingDate]'  
    )   
    ```  
  
6.  <span data-ttu-id="6eced-142">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="6eced-142">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="6eced-143">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `ProcessForecastingAll.dmx` .</span><span class="sxs-lookup"><span data-stu-id="6eced-143">In the **Save As** dialog box, browse to the appropriate folder, and name the file `ProcessForecastingAll.dmx`.</span></span>  
  
8.  <span data-ttu-id="6eced-144">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="6eced-144">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="6eced-145">После окончания выполнения запроса можно создавать прогнозы с использованием обработанных моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-145">After the query has finished running, you can create predictions by using the processed mining models.</span></span> <span data-ttu-id="6eced-146">В следующем занятии будет создано несколько прогнозов на основе созданных моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6eced-146">In the next lesson, you will create several predictions based on the mining models that you created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="6eced-147">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="6eced-147">Next Lesson</span></span>  
 [<span data-ttu-id="6eced-148">Занятие 4: Создание прогнозов на основе временных рядов с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="6eced-148">Lesson 4: Creating Time Series Predictions Using DMX</span></span>](../../2014/tutorials/lesson-4-creating-time-series-predictions-using-dmx.md)  
  
## <a name="see-also"></a><span data-ttu-id="6eced-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="6eced-149">See Also</span></span>  
 <span data-ttu-id="6eced-150">[Требования к обработке и рекомендации &#40;&#41;интеллектуального анализа данных](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6eced-150">[Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span></span>  
 <span data-ttu-id="6eced-151">[&#62;запроса источника данных&#60;](/sql/dmx/source-data-query) </span><span class="sxs-lookup"><span data-stu-id="6eced-151">[&#60;source data query&#62;](/sql/dmx/source-data-query) </span></span>  
 [<span data-ttu-id="6eced-152">OPENQUERY &#40;РАСШИРЕНИЙ ИНТЕЛЛЕКТУАЛЬНОГО АНАЛИЗА ДАННЫХ&#41;</span><span class="sxs-lookup"><span data-stu-id="6eced-152">OPENQUERY &#40;DMX&#41;</span></span>](/sql/dmx/source-data-query-openquery)  
  
  
