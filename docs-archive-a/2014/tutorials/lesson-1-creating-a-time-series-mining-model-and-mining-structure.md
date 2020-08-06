---
title: Занятие 1. Создание модели и структуры интеллектуального анализа данных временных рядов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b201f2b8-9ab5-425b-9ff3-fe321a60a7b7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2513bc3837dd224f6561eb0015ced538ea3add8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656109"
---
# <a name="lesson-1-creating-a-time-series-mining-model-and-mining-structure"></a><span data-ttu-id="2690f-102">Урок 1. Создание модели и структуры интеллектуального анализа данных на основе временных рядов</span><span class="sxs-lookup"><span data-stu-id="2690f-102">Lesson 1: Creating a Time Series Mining Model and Mining Structure</span></span>
  <span data-ttu-id="2690f-103">На этом занятии будет создана модель интеллектуального анализа данных, с помощью которой можно спрогнозировать значения во времени на основании исторических данных.</span><span class="sxs-lookup"><span data-stu-id="2690f-103">In this lesson, you will create a mining model that allows you to predict values over time, based on historical data.</span></span> <span data-ttu-id="2690f-104">После создания модели автоматически будет создана базовая структура, которую можно использовать в качестве основы для дополнительных моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2690f-104">When you create the model, the underlying structure will be generated automatically and can be used as the basis for additional mining models.</span></span>  
  
 <span data-ttu-id="2690f-105">На этом занятии предполагается, что вы знакомы с моделями прогнозирования и требованиями алгоритма временных рядов (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="2690f-105">This lesson assumes that you are familiar with forecasting models and with the requirements of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="2690f-106">Дополнительные сведения см. в статье [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="2690f-106">For more information, see [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span></span>  
  
## <a name="create-mining-model-statement"></a><span data-ttu-id="2690f-107">Инструкция CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="2690f-107">CREATE MINING MODEL Statement</span></span>  
 <span data-ttu-id="2690f-108">Чтобы создать модель интеллектуального анализа данных напрямую и автоматически создать базовую структуру интеллектуального анализа данных, используйте инструкцию [создания модели интеллектуального анализа данных &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) .</span><span class="sxs-lookup"><span data-stu-id="2690f-108">In order to create a mining model directly and automatically generate the underlying mining structure, you use the [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) statement.</span></span> <span data-ttu-id="2690f-109">Код инструкции можно разбить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="2690f-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="2690f-110">присвоение имени модели;</span><span class="sxs-lookup"><span data-stu-id="2690f-110">Naming the model</span></span>  
  
-   <span data-ttu-id="2690f-111">определение временной метки;</span><span class="sxs-lookup"><span data-stu-id="2690f-111">Defining the time stamp</span></span>  
  
-   <span data-ttu-id="2690f-112">определение необязательного ключевого столбца ряда;</span><span class="sxs-lookup"><span data-stu-id="2690f-112">Defining the optional series key column</span></span>  
  
-   <span data-ttu-id="2690f-113">определение прогнозируемого атрибута или атрибутов.</span><span class="sxs-lookup"><span data-stu-id="2690f-113">Defining the predictable attribute or attributes</span></span>  
  
 <span data-ttu-id="2690f-114">В следующем фрагменте показан стандартный пример инструкции CREATE MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="2690f-114">The following is a generic example of the CREATE MINING MODEL statement:</span></span>  
  
```  
CREATE MINING MODEL [<Mining Structure Name>]  
(  
   <key columns>,  
   <predictable attribute columns>  
)  
USING <algorithm name>([parameter list])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="2690f-115">Первая строчка кода определяет имя модели интеллектуального анализа данных:</span><span class="sxs-lookup"><span data-stu-id="2690f-115">The first line of the code defines the name of the mining model:</span></span>  
  
```  
CREATE MINING MODEL [Mining Model Name]  
```  
  
 <span data-ttu-id="2690f-116">Службы Analysis Services автоматически формируют имя базовой структуры путем добавления строки «_structure» к имени модели, что гарантирует несовпадение имени структуры и модели.</span><span class="sxs-lookup"><span data-stu-id="2690f-116">Analysis Services automatically generates a name for the underlying structure, by appending "_structure" to the model name, which ensures that the structure name is unique from the model name.</span></span> <span data-ttu-id="2690f-117">Сведения об именовании объекта в расширениях интеллектуального анализа данных см. в разделе [идентификаторы &#40;&#41;расширений интеллектуального анализа данных ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="2690f-117">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="2690f-118">В следующей строке кода задается ключевой столбец модели интеллектуального анализа данных, который в случае с моделью временных рядов уникально определяет временной этап в исходных данных.</span><span class="sxs-lookup"><span data-stu-id="2690f-118">The next line of the code defines the key column for the mining model, which in the case of a time series model uniquely identifies a time step in the source data.</span></span> <span data-ttu-id="2690f-119">Временной этап определяется с помощью ключевых слов `KEY TIME` после имени столбца и типов данных.</span><span class="sxs-lookup"><span data-stu-id="2690f-119">The time step is identified with the `KEY TIME` keywords after the column name and data types.</span></span> <span data-ttu-id="2690f-120">Если модель временных рядов имеет отдельный ключ ряда, она определяется с помощью ключевого слова `KEY`.</span><span class="sxs-lookup"><span data-stu-id="2690f-120">If the time series model has a separate series key, it is identified by using the `KEY` keyword.</span></span>  
  
```  
<key columns>  
```  
  
 <span data-ttu-id="2690f-121">Следующая строка кода используется для определения столбцов в прогнозируемой модели.</span><span class="sxs-lookup"><span data-stu-id="2690f-121">The next line of the code is used to define the columns in the model that will be predicted.</span></span> <span data-ttu-id="2690f-122">Отдельная модель интеллектуального анализа данных может иметь несколько прогнозируемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="2690f-122">You can have multiple predictable attributes in a single mining model.</span></span> <span data-ttu-id="2690f-123">В таком случае алгоритм временных рядов (Майкрософт) создает отдельный анализ для каждого ряда:</span><span class="sxs-lookup"><span data-stu-id="2690f-123">When there are multiple predictable attributes, the Microsoft Time Series algorithm generates a separate analysis for each series:</span></span>  
  
```  
<predictable attribute columns>  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="2690f-124">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="2690f-124">Lesson Tasks</span></span>  
 <span data-ttu-id="2690f-125">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="2690f-125">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="2690f-126">Создание нового пустого запроса</span><span class="sxs-lookup"><span data-stu-id="2690f-126">Create a new blank query</span></span>  
  
-   <span data-ttu-id="2690f-127">Изменение запроса, чтобы создать модель интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="2690f-127">Alter the query to create the mining model</span></span>  
  
-   <span data-ttu-id="2690f-128">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="2690f-128">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="2690f-129">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="2690f-129">Creating the Query</span></span>  
 <span data-ttu-id="2690f-130">На первом этапе необходимо подключиться к экземпляру служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и создать новый DMX-запрос в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2690f-130">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="2690f-131">Создание нового DMX-запроса в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2690f-131">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="2690f-132">Откройте [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2690f-132">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2690f-133">В диалоговом окне **соединение с сервером** в поле **тип сервера**выберите **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="2690f-133">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="2690f-134">В поле **имя сервера**введите `LocalHost` или имя экземпляра [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , к которому необходимо подключиться для этого занятия.</span><span class="sxs-lookup"><span data-stu-id="2690f-134">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="2690f-135">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="2690f-135">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="2690f-136">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="2690f-136">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="2690f-137">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="2690f-137">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="2690f-138">Изменение запроса</span><span class="sxs-lookup"><span data-stu-id="2690f-138">Altering the Query</span></span>  
 <span data-ttu-id="2690f-139">Следующим шагом будет изменение инструкции CREATE MINING MODEL, чтобы создать модель интеллектуального анализа данных, используемую для составления прогнозов, а также ее базовую структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2690f-139">The next step is to modify the CREATE MINING MODEL statement to create the mining model used for forecasting, together with its underlying mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-model-statement"></a><span data-ttu-id="2690f-140">Настройка инструкции CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="2690f-140">To customize the CREATE MINING MODEL statement</span></span>  
  
1.  <span data-ttu-id="2690f-141">В редакторе запросов скопируйте общий пример инструкции CREATE MINING MODEL в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="2690f-141">In Query Editor, copy the generic example of the CREATE MINING MODEL statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="2690f-142">Вместо</span><span class="sxs-lookup"><span data-stu-id="2690f-142">Replace the following:</span></span>  
  
    ```  
    [mining model name]   
    ```  
  
     <span data-ttu-id="2690f-143">на:</span><span class="sxs-lookup"><span data-stu-id="2690f-143">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
3.  <span data-ttu-id="2690f-144">Вместо</span><span class="sxs-lookup"><span data-stu-id="2690f-144">Replace the following:</span></span>  
  
    ```  
    <key columns>  
    ```  
  
     <span data-ttu-id="2690f-145">на:</span><span class="sxs-lookup"><span data-stu-id="2690f-145">with:</span></span>  
  
    ```  
    [Reporting Date] DATE KEY TIME,  
    [Model Region] TEXT KEY  
    ```  
  
     <span data-ttu-id="2690f-146">Ключевое слово `TIME KEY` указывает на то, что столбец ReportingDate содержит значения временных этапов, используемые для определения порядка следования значений.</span><span class="sxs-lookup"><span data-stu-id="2690f-146">The `TIME KEY` keyword indicates that the ReportingDate column contains the time step values used to order the values.</span></span> <span data-ttu-id="2690f-147">Временными этапами могут быть даты и значения времени, целые числа или любой другой тип упорядоченных данных при условии, что значения уникальны, а данные отсортированы.</span><span class="sxs-lookup"><span data-stu-id="2690f-147">Time steps can be dates and times, integers, or any ordered data type, so long as the values are unique and the data is sorted.</span></span>  
  
     <span data-ttu-id="2690f-148">Ключевые слова `TEXT` и `KEY` указывают на то, что столбец ModelRegion содержит дополнительный ключ ряда.</span><span class="sxs-lookup"><span data-stu-id="2690f-148">The `TEXT` and `KEY` keywords indicate that the ModelRegion column contains an additional series key.</span></span> <span data-ttu-id="2690f-149">Допускается использование только одного ключа ряда, при этом значения в столбце должны отличаться друг от друга.</span><span class="sxs-lookup"><span data-stu-id="2690f-149">You can have only one series key, and the values in the column must be distinct.</span></span>  
  
4.  <span data-ttu-id="2690f-150">Вместо</span><span class="sxs-lookup"><span data-stu-id="2690f-150">Replace the following:</span></span>  
  
    ```  
    < predictable attribute columns> )  
    ```  
  
     <span data-ttu-id="2690f-151">на:</span><span class="sxs-lookup"><span data-stu-id="2690f-151">with:</span></span>  
  
    ```  
    [Quantity] LONG CONTINUOUS PREDICT,  
    [Amount] DOUBLE CONTINUOUS PREDICT  
    )  
    ```  
  
5.  <span data-ttu-id="2690f-152">Вместо</span><span class="sxs-lookup"><span data-stu-id="2690f-152">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([parameter list])  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="2690f-153">на:</span><span class="sxs-lookup"><span data-stu-id="2690f-153">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series(AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="2690f-154">Параметр алгоритма `AUTO_DETECT_PERIODICITY` = 0,8 указывает на то, что алгоритм должен обнаруживать циклы в данных.</span><span class="sxs-lookup"><span data-stu-id="2690f-154">The algorithm parameter, `AUTO_DETECT_PERIODICITY` = 0.8, indicates that you want the algorithm to detect cycles in the data.</span></span> <span data-ttu-id="2690f-155">Установка значения, близкого к 1, позволяет обнаружить множество шаблонов, но может замедлить процесс обработки.</span><span class="sxs-lookup"><span data-stu-id="2690f-155">Setting this value closer to 1 favors the discovery of many patterns but can slow processing.</span></span>  
  
     <span data-ttu-id="2690f-156">Параметр алгоритма `FORECAST_METHOD` задает алгоритм анализа данных ARTXP или ARIMA или сочетание обоих алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="2690f-156">The algorithm parameter, `FORECAST_METHOD`, indicates whether you want the data to be analyzed using ARTXP, ARIMA, or a mixture of both.</span></span>  
  
     <span data-ttu-id="2690f-157">Ключевое слово `WITH DRILLTHROUGH` обеспечивает возможность просмотра подробной статистики в исходных данных после завершения создания модели.</span><span class="sxs-lookup"><span data-stu-id="2690f-157">The keyword, `WITH DRILLTHROUGH`, specify that you want to be able to view detailed statistics in the source data after the model is complete.</span></span> <span data-ttu-id="2690f-158">Добавьте это предложение в том случае, если нужно просматривать модель с помощью средства просмотра временных рядов (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="2690f-158">You must add this clause if you want to browse the model by using the Microsoft Time Series Viewer.</span></span> <span data-ttu-id="2690f-159">Для создания прогноза оно не требуется.</span><span class="sxs-lookup"><span data-stu-id="2690f-159">It is not required for prediction.</span></span>  
  
     <span data-ttu-id="2690f-160">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2690f-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING MODEL [Forecasting_MIXED]  
         (  
        [Reporting Date] DATE KEY TIME,  
        [Model Region] TEXT KEY,  
        [Quantity] LONG CONTINUOUS PREDICT,  
        [Amount] DOUBLE CONTINUOUS PREDICT  
        )  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
  
    ```  
  
6.  <span data-ttu-id="2690f-161">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="2690f-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="2690f-162">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Forecasting_MIXED.dmx` .</span><span class="sxs-lookup"><span data-stu-id="2690f-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_MIXED.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="2690f-163">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="2690f-163">Executing the Query</span></span>  
 <span data-ttu-id="2690f-164">На последнем шаге нужно выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="2690f-164">The final step is to execute the query.</span></span> <span data-ttu-id="2690f-165">Создав и сохранив запрос, его необходимо выполнить, чтобы сформировать модель интеллектуального анализа данных и соответствующую структуру на сервере.</span><span class="sxs-lookup"><span data-stu-id="2690f-165">After a query is created and saved, it needs to be executed to create the mining model and its mining structure on the server.</span></span> <span data-ttu-id="2690f-166">Дополнительные сведения о выполнении запросов в редакторе запросов см. в разделе [ядро СУБД редактор запросов &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="2690f-166">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="2690f-167">Порядок выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="2690f-167">To execute the query</span></span>  
  
-   <span data-ttu-id="2690f-168">На панели инструментов редактора запросов нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2690f-168">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="2690f-169">Состояние запроса отображается на вкладке **сообщения** в нижней части редактора запросов после завершения выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="2690f-169">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="2690f-170">Сообщение должно выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2690f-170">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="2690f-171">На сервере теперь существует новая структура с именем **Forecasting_MIXED_Structure** , а также связанная с ней модель интеллектуального анализа данных **Forecasting_MIXED**.</span><span class="sxs-lookup"><span data-stu-id="2690f-171">A new structure named **Forecasting_MIXED_Structure** now exists on the server, together with the related mining model **Forecasting_MIXED**.</span></span>  
  
 <span data-ttu-id="2690f-172">На следующем занятии модель интеллектуального анализа данных будет добавлена в только что созданную структуру **Forecasting_MIXEDного** интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="2690f-172">In the next lesson, you will add a mining model to the **Forecasting_MIXED** mining structure that you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="2690f-173">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="2690f-173">Next Lesson</span></span>  
 [<span data-ttu-id="2690f-174">Урок 2. Добавление моделей в структуру интеллектуального анализа данных на основе временных рядов</span><span class="sxs-lookup"><span data-stu-id="2690f-174">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)  
  
## <a name="see-also"></a><span data-ttu-id="2690f-175">См. также</span><span class="sxs-lookup"><span data-stu-id="2690f-175">See Also</span></span>  
 <span data-ttu-id="2690f-176">[Содержимое модели интеллектуального анализа данных для моделей временных рядов &#40;Analysis Services-интеллектуальный анализ данных&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="2690f-176">[Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="2690f-177">Microsoft Time Series Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="2690f-177">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
