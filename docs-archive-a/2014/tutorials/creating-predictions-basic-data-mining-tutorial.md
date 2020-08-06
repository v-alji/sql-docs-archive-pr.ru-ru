---
title: Создание прогнозов (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a8410ed2-bb98-4d51-a9eb-b239be1201c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 456aec6c6b9d0d1a5d0ee1d9949507a37577130c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727525"
---
# <a name="creating-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="28d65-102">Создание прогнозов (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="28d65-102">Creating Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="28d65-103">После того как вы проверили точность моделей интеллектуального анализа данных и решили, что результаты удовлетворены, можно создать прогнозы с помощью конструктор запросов прогнозирования на вкладке **Прогноз модели интеллектуального анализа** данных в конструкторе интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="28d65-103">After you have tested the accuracy of your mining models and decided that you are satisfied with the results, you can then generate predictions by using the Prediction Query Builder on the **Mining Model Prediction** tab in the Data Mining Designer.</span></span>  
  
 <span data-ttu-id="28d65-104">Построитель прогнозирующих запросов имеет три представления.</span><span class="sxs-lookup"><span data-stu-id="28d65-104">The Prediction Query Builder has three views.</span></span> <span data-ttu-id="28d65-105">С помощью представлений **конструирования** и **запросов** можно создавать и анализировать запросы.</span><span class="sxs-lookup"><span data-stu-id="28d65-105">With the **Design** and **Query** views, you can build and examine your query.</span></span> <span data-ttu-id="28d65-106">Затем можно выполнить запрос и просмотреть результаты в представлении **результатов** .</span><span class="sxs-lookup"><span data-stu-id="28d65-106">You can then run the query and view the results in the **Result** view.</span></span>  
  
 <span data-ttu-id="28d65-107">Во всех прогнозирующих запросах используется DMX — язык расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="28d65-107">All prediction queries use DMX, which is short for the Data Mining Extensions (DMX) language.</span></span> <span data-ttu-id="28d65-108">Синтаксис расширения интеллектуального анализа данных похож на синтаксис T-SQL, но служит для написания запросов к объектам интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="28d65-108">DMX has syntax like that of T-SQL but is used for queries against data mining objects.</span></span> <span data-ttu-id="28d65-109">Хотя синтаксис расширений интеллектуального анализа данных не является сложным, используя построитель запросов, как и этот, или один из [SQL Server надстроек интеллектуального анализа данных для Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), значительно упрощает выбор входов и выражений сборки, поэтому мы настоятельно рекомендуем изучить основы.</span><span class="sxs-lookup"><span data-stu-id="28d65-109">Although DMX syntax is not complicated, using a query builder like this one, or the one in the [SQL Server Data Mining Add-Ins for Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), makes it much easier to select inputs and build expressions, so we highly recommend that you learn the basics.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="28d65-110">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="28d65-110">Creating the Query</span></span>  
 <span data-ttu-id="28d65-111">Первым шагом в создании прогнозирующего запроса является выбор модели интеллектуального анализа данных и входной таблицы.</span><span class="sxs-lookup"><span data-stu-id="28d65-111">The first step in creating a prediction query is to select a mining model and input table.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="28d65-112">Выбор модели и входной таблицы</span><span class="sxs-lookup"><span data-stu-id="28d65-112">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="28d65-113">На вкладке **Прогнозирование моделей интеллектуального анализа** конструктора интеллектуального анализа данных в поле **модель интеллектуального анализа** нажмите кнопку **выбрать модель**.</span><span class="sxs-lookup"><span data-stu-id="28d65-113">On the **Mining Model Prediction** tab of Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="28d65-114">В диалоговом окне **Выбор модели интеллектуального анализа данных** перейдите по дереву к структуре **целевой рассылки** , разверните структуру, выберите `TM_Decision_Tree` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28d65-114">In the **Select Mining Model** dialog box, navigate through the tree to the **Targeted Mailing** structure, expand the structure, select `TM_Decision_Tree`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="28d65-115">В поле **Выбор входных таблиц** нажмите кнопку **выбрать таблицу вариантов**.</span><span class="sxs-lookup"><span data-stu-id="28d65-115">In the **Select Input Table(s)** box, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="28d65-116">В диалоговом окне **Выбор таблицы** в списке **источник данных** выберите представление источника данных [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28d65-116">In the **Select Table** dialog box, in the **Data Source** list, select the data source view [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
5.  <span data-ttu-id="28d65-117">В поле **имя таблицы или представления**выберите таблицу **ProspectiveBuyer (dbo)** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28d65-117">In **Table/View Name**, select the **ProspectiveBuyer (dbo)** table, and then click **OK**.</span></span>  
  
     <span data-ttu-id="28d65-118">`ProspectiveBuyer`Таблица наиболее похожа на таблицу вариантов **vTargetMail** .</span><span class="sxs-lookup"><span data-stu-id="28d65-118">The `ProspectiveBuyer` table most closely resembles the **vTargetMail** case table.</span></span>  
  
## <a name="mapping-the-columns"></a><span data-ttu-id="28d65-119">Сопоставление столбцов</span><span class="sxs-lookup"><span data-stu-id="28d65-119">Mapping the Columns</span></span>  
 <span data-ttu-id="28d65-120">После выбора входной таблицы в построителе прогнозирующих запросов будет создано сопоставление по умолчанию между моделью интеллектуального анализа данных и таблицей входных данных на основе имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="28d65-120">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="28d65-121">По крайней мере один столбец структуры необходимо сопоставить со столбцом внешних данных.</span><span class="sxs-lookup"><span data-stu-id="28d65-121">At least one column from the structure must match a column in the external data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="28d65-122">Данные, которые используются для определения точности моделей, должны содержать столбец, который может быть сопоставлен с прогнозируемым столбцом.</span><span class="sxs-lookup"><span data-stu-id="28d65-122">The data that you use to determine the accuracy of the models must contain a column that can be mapped to the predictable column.</span></span> <span data-ttu-id="28d65-123">Если такой столбец не существует, то можно создать его с пустыми значениями, однако этот столбец должен иметь тот же тип данных, что и прогнозируемый.</span><span class="sxs-lookup"><span data-stu-id="28d65-123">If such a column does not exist, you can create one with empty values, but it must have the same data type as the predictable column.</span></span>  
  
#### <a name="to-map-the-inputs-to-the-model"></a><span data-ttu-id="28d65-124">Сопоставление входных данных с моделью</span><span class="sxs-lookup"><span data-stu-id="28d65-124">To map the inputs to the model</span></span>  
  
1.  <span data-ttu-id="28d65-125">Щелкните правой кнопкой мыши линии, соединяющие окно **модель интеллектуального анализа данных** с окном **Выбор входных таблиц** , и выберите пункт **Изменить соединения**.</span><span class="sxs-lookup"><span data-stu-id="28d65-125">Right-click the lines connecting the **Mining Model** window to the **Select Input Table** window, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="28d65-126">Обратите внимание, что сопоставляется не каждый столбец.</span><span class="sxs-lookup"><span data-stu-id="28d65-126">Notice that not every column is mapped.</span></span> <span data-ttu-id="28d65-127">Будут добавлены сопоставления для нескольких **столбцов таблицы**.</span><span class="sxs-lookup"><span data-stu-id="28d65-127">We will add mappings for several **Table Columns**.</span></span> <span data-ttu-id="28d65-128">Кроме того, сформируем новый столбец с датой рождения, исходя из текущего столбца данных так, чтобы столбцы лучше совпадали.</span><span class="sxs-lookup"><span data-stu-id="28d65-128">We will also generate a new birth date column based on the current date column, so that the columns match better.</span></span>  
  
2.  <span data-ttu-id="28d65-129">В разделе **столбец таблицы**щелкните `Bike Buyer` ячейку и выберите ProspectiveBuyer. Unknown из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="28d65-129">Under **Table Column**, click the `Bike Buyer` cell and select ProspectiveBuyer.Unknown from the dropdown.</span></span>  
  
     <span data-ttu-id="28d65-130">При этом прогнозируемый столбец [Bike Buyer] сопоставляется со столбцом входной таблицы.</span><span class="sxs-lookup"><span data-stu-id="28d65-130">This maps the predictable column, [Bike Buyer], to an input table column.</span></span>  
  
3.  <span data-ttu-id="28d65-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28d65-131">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="28d65-132">В **Обозреватель решений**щелкните правой кнопкой мыши представление источника данных **целевой рассылки** и выберите пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="28d65-132">In **Solution Explorer**, right-click the **Targeted Mailing** data source view and select **View Designer**.</span></span>  
  
5.  <span data-ttu-id="28d65-133">Щелкните правой кнопкой мыши таблицу ProspectiveBuyer и выберите **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="28d65-133">Right-click the table, ProspectiveBuyer, and select **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="28d65-134">В диалоговом окне **Создание именованного вычисления** в поле **имя столбца**введите `calcAge` .</span><span class="sxs-lookup"><span data-stu-id="28d65-134">In the **Create Named Calculation** dialog box, for **Column name**, type `calcAge`.</span></span>  
  
7.  <span data-ttu-id="28d65-135">В качестве **описания**введите **вычислить возраст на основе даты рождения**.</span><span class="sxs-lookup"><span data-stu-id="28d65-135">For **Description**, type **Calculate age based on birthdate**.</span></span>  
  
8.  <span data-ttu-id="28d65-136">В поле **выражение** введите `DATEDIFF(YYYY,[BirthDate],getdate())` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28d65-136">In the **Expression** box, type `DATEDIFF(YYYY,[BirthDate],getdate())` and then click **OK**.</span></span>  
  
     <span data-ttu-id="28d65-137">Так как входная таблица не имеет столбца **Age** , соответствующего значению в модели, это выражение можно использовать для вычисления возраста клиента из столбца «ДеньРождения» во входной таблице.</span><span class="sxs-lookup"><span data-stu-id="28d65-137">Because the input table has no **Age** column corresponding to the one in the model, you can use this expression to calculate customer age from the BirthDate column in the input table.</span></span> <span data-ttu-id="28d65-138">Поскольку **Age** был определен как самый влиятельные столбец для прогнозирования приобретения велосипеда, он должен существовать как в модели, так и во входной таблице.</span><span class="sxs-lookup"><span data-stu-id="28d65-138">Since **Age** was identified as the most influential column for predicting bike buying, it must exist in both the model and in the input table.</span></span>  
  
9. <span data-ttu-id="28d65-139">В конструкторе интеллектуального анализа данных выберите вкладку **Прогноз модели интеллектуального анализа** и снова откройте окно **Изменение подключений** .</span><span class="sxs-lookup"><span data-stu-id="28d65-139">In Data Mining Designer, select the **Mining Model Prediction** tab and re-open the **Modify Connections** window.</span></span>  
  
10. <span data-ttu-id="28d65-140">В разделе **столбец таблицы**щелкните ячейку **Age** и выберите ProspectiveBuyer. Calc из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="28d65-140">Under **Table Column**, click the **Age** cell and select ProspectiveBuyer.calcAge from the dropdown.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="28d65-141">Если столбец не появился в списке, то может потребоваться обновить определение представления источников данных, загруженного в конструктор.</span><span class="sxs-lookup"><span data-stu-id="28d65-141">If you do not see the column in the list, you might have to refresh the definition of the data source view that is loaded in the designer.</span></span> <span data-ttu-id="28d65-142">Для этого в меню **файл** выберите **сохранить все**, а затем закройте и снова откройте проект в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="28d65-142">To do this, from the **File** menu, select **Save all**, and then close and re-open the project in the designer.</span></span>  
  
11. <span data-ttu-id="28d65-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28d65-143">Click **OK**.</span></span>  
  
## <a name="designing-the-prediction-query"></a><span data-ttu-id="28d65-144">Проектирование прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="28d65-144">Designing the Prediction Query</span></span>  
  
1.  <span data-ttu-id="28d65-145">Первой кнопкой на панели инструментов вкладки **Прогноз модели интеллектуального анализа данных** является **Переключение в режим конструктора/переключиться на представление "результат"/"перейти к представлению запроса** ".</span><span class="sxs-lookup"><span data-stu-id="28d65-145">The first button on the toolbar of the **Mining Model Prediction** tab is the **Switch to design view / Switch to result view / Switch to query view** button.</span></span> <span data-ttu-id="28d65-146">Нажмите кнопку со стрелкой вниз на этой кнопке и выберите пункт **конструктор**.</span><span class="sxs-lookup"><span data-stu-id="28d65-146">Click the down arrow on this button, and select **Design**.</span></span>  
  
2.  <span data-ttu-id="28d65-147">В сетке на вкладке **Прогноз модели интеллектуального анализа данных** щелкните ячейку в первой пустой строке **исходного** столбца, а затем выберите **функция прогнозирования**.</span><span class="sxs-lookup"><span data-stu-id="28d65-147">In the grid on the **Mining Model Prediction** tab, click the cell in the first empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
3.  <span data-ttu-id="28d65-148">В строке **функция прогнозирования** в столбце **поле** выберите `PredictProbability` .</span><span class="sxs-lookup"><span data-stu-id="28d65-148">In the **Prediction Function** row, in the **Field** column, select `PredictProbability`.</span></span>  
  
     <span data-ttu-id="28d65-149">В столбце **псевдоним** той же строки введите **вероятность результата**.</span><span class="sxs-lookup"><span data-stu-id="28d65-149">In the **Alias** column of the same row, type **Probability of result**.</span></span>  
  
4.  <span data-ttu-id="28d65-150">В расположенном выше окне **модель интеллектуального анализа данных** выберите и перетащите [Bike Buyer] в ячейку **критерий или аргумент** .</span><span class="sxs-lookup"><span data-stu-id="28d65-150">From the **Mining Model** window above, select and drag [Bike Buyer] into the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="28d65-151">Если вы разрешите Go, [TM_Decision_Tree]. [Покупатель велосипеда] отображается в ячейке **критерий или аргумента** .</span><span class="sxs-lookup"><span data-stu-id="28d65-151">When you let go, [TM_Decision_Tree].[Bike Buyer] appears in the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="28d65-152">Таким образом определяется целевой столбец для функции `PredictProbability`.</span><span class="sxs-lookup"><span data-stu-id="28d65-152">This specifies the target column for the `PredictProbability` function.</span></span> <span data-ttu-id="28d65-153">Дополнительные сведения о функциях см. в разделе [расширения интеллектуального анализа данных &#40;DMX&#41; функция Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="28d65-153">For more information about functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
5.  <span data-ttu-id="28d65-154">Щелкните следующую пустую строку в **исходном** столбце, а затем выберите **TM_Decision_Tree** модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="28d65-154">Click the next empty row in the **Source** column, and then select **TM_Decision_Tree** mining model.</span></span>  
  
6.  <span data-ttu-id="28d65-155">В `TM_Decision_Tree` строке в столбце **поле** выберите `Bike Buyer` .</span><span class="sxs-lookup"><span data-stu-id="28d65-155">In the `TM_Decision_Tree` row, in the **Field** column, select `Bike Buyer`.</span></span>  
  
7.  <span data-ttu-id="28d65-156">В `TM_Decision_Tree` строке в столбце **критерий или аргумент** введите `=1` .</span><span class="sxs-lookup"><span data-stu-id="28d65-156">In the `TM_Decision_Tree` row, in the **Criteria/Argument** column, type `=1`.</span></span>  
  
8.  <span data-ttu-id="28d65-157">Щелкните следующую пустую строку в **исходном** столбце, а затем выберите **ProspectiveBuyer Table (таблица**).</span><span class="sxs-lookup"><span data-stu-id="28d65-157">Click the next empty row in the **Source** column, and then select **ProspectiveBuyer table**.</span></span>  
  
9. <span data-ttu-id="28d65-158">В `ProspectiveBuyer` строке в столбце **поле** выберите **проспективебуйеркэй**.</span><span class="sxs-lookup"><span data-stu-id="28d65-158">In the `ProspectiveBuyer` row, in the **Field** column, select **ProspectiveBuyerKey**.</span></span>  
  
     <span data-ttu-id="28d65-159">При этом к прогнозирующему запросу добавляется уникальный идентификатор, который позволяет определить, кто, скорее всего, будет или не будет покупать велосипед.</span><span class="sxs-lookup"><span data-stu-id="28d65-159">This adds the unique identifier to the prediction query so that you can identify who is and who is not likely to buy a bicycle.</span></span>  
  
10. <span data-ttu-id="28d65-160">Добавьте еще пять строк в сетку.</span><span class="sxs-lookup"><span data-stu-id="28d65-160">Add five more rows to the grid.</span></span> <span data-ttu-id="28d65-161">Для каждой строки выберите **таблицу ProspectiveBuyer** в качестве **источника** , а затем добавьте в ячейки **поля** следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="28d65-161">For each row, select **ProspectiveBuyer table** as the **Source** and then add the following columns in the **Field** cells:</span></span>  
  
    -   <span data-ttu-id="28d65-162">calcAge</span><span class="sxs-lookup"><span data-stu-id="28d65-162">calcAge</span></span>  
  
    -   <span data-ttu-id="28d65-163">LastName</span><span class="sxs-lookup"><span data-stu-id="28d65-163">LastName</span></span>  
  
    -   <span data-ttu-id="28d65-164">FirstName</span><span class="sxs-lookup"><span data-stu-id="28d65-164">FirstName</span></span>  
  
    -   <span data-ttu-id="28d65-165">AddressLine1</span><span class="sxs-lookup"><span data-stu-id="28d65-165">AddressLine1</span></span>  
  
    -   <span data-ttu-id="28d65-166">AddressLine2</span><span class="sxs-lookup"><span data-stu-id="28d65-166">AddressLine2</span></span>  
  
 <span data-ttu-id="28d65-167">Наконец, выполните запрос и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="28d65-167">Finally, run the query and browse the results.</span></span>  
  
 <span data-ttu-id="28d65-168">**Конструктор запросов прогнозирования** также включает следующие элементы управления:</span><span class="sxs-lookup"><span data-stu-id="28d65-168">The **Prediction Query Builder** also includes these controls:</span></span>  
  
-   <span data-ttu-id="28d65-169">Флажок " **Показывать** "</span><span class="sxs-lookup"><span data-stu-id="28d65-169">**Show** check box</span></span>  
  
     <span data-ttu-id="28d65-170">Позволяет удалять предложения из запроса без удаления их из конструктора.</span><span class="sxs-lookup"><span data-stu-id="28d65-170">Lets you remove clauses from the query without having to delete them from the designer.</span></span> <span data-ttu-id="28d65-171">Это может потребоваться при работе со сложными запросами, когда возникает необходимость сохранять их синтаксис, не прибегая к копированию и вставке кода DMX в окне редактирования.</span><span class="sxs-lookup"><span data-stu-id="28d65-171">This can be useful when you are working with complex queries and want to preserve syntax without having to copy and paste DMX into the window.</span></span>  
  
-   <span data-ttu-id="28d65-172">**Группа**</span><span class="sxs-lookup"><span data-stu-id="28d65-172">**Group**</span></span>  
  
     <span data-ttu-id="28d65-173">Вставляет открывающую (левую) скобку в начале выделенной строки или закрывающую (правую) скобку в конце текущей строки.</span><span class="sxs-lookup"><span data-stu-id="28d65-173">Inserts an opening (left) parentheses at the beginning of the selected line, or inserts a closing (right) parenthesis at the end of the current line.</span></span>  
  
-   <span data-ttu-id="28d65-174">**И (ИЛИ)**</span><span class="sxs-lookup"><span data-stu-id="28d65-174">**AND/OR**</span></span>  
  
     <span data-ttu-id="28d65-175">Вставляет оператор `AND` или оператор `OR` непосредственно после текущей функции или столбца.</span><span class="sxs-lookup"><span data-stu-id="28d65-175">Inserts the  `AND` operator or the `OR` operator immediately after the current function or column.</span></span>  
  
#### <a name="to-run-the-query-and-view-results"></a><span data-ttu-id="28d65-176">Выполнение запроса и просмотр результатов</span><span class="sxs-lookup"><span data-stu-id="28d65-176">To run the query and view results</span></span>  
  
1.  <span data-ttu-id="28d65-177">На вкладке **Прогноз модели интеллектуального анализа данных** нажмите кнопку **результат** .</span><span class="sxs-lookup"><span data-stu-id="28d65-177">In the **Mining Model Prediction** tab, select the **Result** button.</span></span>  
  
2.  <span data-ttu-id="28d65-178">После выполнения запроса отображаются результаты для просмотра.</span><span class="sxs-lookup"><span data-stu-id="28d65-178">After the query runs and the results are displayed, you can review the results.</span></span>  
  
     <span data-ttu-id="28d65-179">На вкладке **Прогноз модели интеллектуального анализа данных** отображаются контактные данные потенциальных клиентов, которые, скорее всего, будут покупателями велосипедов.</span><span class="sxs-lookup"><span data-stu-id="28d65-179">The **Mining Model Prediction** tab displays contact information for potential customers who are likely to be bike buyers.</span></span> <span data-ttu-id="28d65-180">В столбце **вероятность результата** указывается вероятность исходящего прогноза.</span><span class="sxs-lookup"><span data-stu-id="28d65-180">The **Probability of result** column indicates the probability of the prediction being correct.</span></span> <span data-ttu-id="28d65-181">Эти результаты можно использовать, чтобы определить, для каких потенциальных заказчиков следует выполнить прямую почтовую рассылку.</span><span class="sxs-lookup"><span data-stu-id="28d65-181">You can use these results to determine which potential customers to target for the mailing.</span></span>  
  
3.  <span data-ttu-id="28d65-182">На этом этапе можно сохранить результаты.</span><span class="sxs-lookup"><span data-stu-id="28d65-182">At this point, you can save the results.</span></span> <span data-ttu-id="28d65-183">Имеются три параметра.</span><span class="sxs-lookup"><span data-stu-id="28d65-183">You have three options:</span></span>  
  
    -   <span data-ttu-id="28d65-184">Щелкните правой кнопкой мыши строку данных в результатах и выберите **Копировать** , чтобы сохранить только это значение (и заголовок столбца) в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="28d65-184">Right-click a row of data in the results, and select **Copy** to save just that value (and the column heading) to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="28d65-185">Щелкните правой кнопкой мыши любую строку результатов и выберите команду **Копировать все** , чтобы скопировать весь результирующий набор, включая заголовки столбцов, в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="28d65-185">Right-click any row in the results, and select **Copy All** to copy the entire result set, including column headings, to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="28d65-186">Щелкните **сохранить результат запроса** , чтобы сохранить результаты непосредственно в базу данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="28d65-186">Click **Save query result** to save the results directly to a database as follows:</span></span>  
  
        1.  <span data-ttu-id="28d65-187">В диалоговом окне **Сохранение результата запроса интеллектуального анализа данных** выберите источник данных или определите новый источник данных.</span><span class="sxs-lookup"><span data-stu-id="28d65-187">In the **Save Data Mining Query Result** dialog box, select a data source, or define a new data source.</span></span>  
  
        2.  <span data-ttu-id="28d65-188">Введите имя таблицы, которая будет хранить результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="28d65-188">Type a name for the table that will contain the query results.</span></span>  
  
        3.  <span data-ttu-id="28d65-189">Используйте параметр **Добавить в DSV**, чтобы создать таблицу и добавить ее в существующее представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="28d65-189">Use the option, **Add to DSV**, to create the table and add it to an existing data source view.</span></span> <span data-ttu-id="28d65-190">Это полезно, если требуется, чтобы все связанные таблицы для модели, такие как обучающие данные, исходные данные и результаты запроса, были в одном и том же представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="28d65-190">This is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source view.</span></span>  
  
        4.  <span data-ttu-id="28d65-191">Используйте параметр **перезаписывать, если существует**, чтобы обновить существующую таблицу с самыми последними результатами.</span><span class="sxs-lookup"><span data-stu-id="28d65-191">Use the option, **Overwrite if exists**, to update an existing table with the latest results.</span></span>  
  
             <span data-ttu-id="28d65-192">Необходимо использовать параметр перезаписи таблицы при добавлении любых столбцов к прогнозирующему запросу, изменении имен или типов данных любых столбцов в прогнозирующем запросе или при выполнении любых инструкций ALTER для целевой таблицы.</span><span class="sxs-lookup"><span data-stu-id="28d65-192">You must use the option to overwrite the table if you have added any columns to the prediction query, changed the names or data types of any columns in the prediction query, or if you have run any ALTER statements on the destination table.</span></span>  
  
             <span data-ttu-id="28d65-193">Кроме того, если несколько столбцов имеют одно и то же имя (например, **выражение**имени столбца по умолчанию), необходимо создать псевдоним для столбцов с повторяющимися именами, иначе при попытке конструктора сохранить результаты в SQL Server будет возникать ошибка.</span><span class="sxs-lookup"><span data-stu-id="28d65-193">Also, if multiple columns have the same name (for example, the default column name **Expression**) you must create an alias for the columns with duplicate names, or an error will be raised when the designer tries to save the results to SQL Server.</span></span> <span data-ttu-id="28d65-194">Причина в том, что SQL Server не разрешает применять несколько столбцов с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="28d65-194">The reason is that SQL Server does not allow multiple columns to have the same name.</span></span>  
  
             <span data-ttu-id="28d65-195">Дополнительные сведения см. в разделе [диалоговое окно "сохранение результата запроса интеллектуального анализа данных" &#40;представление прогноза модели интеллектуального анализа&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span><span class="sxs-lookup"><span data-stu-id="28d65-195">For more information, see [Save Data Mining Query Result Dialog Box &#40;Mining Model Prediction View&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="28d65-196">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="28d65-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="28d65-197">Использование детализации в данных структуры &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="28d65-197">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="28d65-198">См. также:</span><span class="sxs-lookup"><span data-stu-id="28d65-198">See Also</span></span>  
 [<span data-ttu-id="28d65-199">Создание прогнозирующего запроса с помощью построителя прогнозирующих запросов</span><span class="sxs-lookup"><span data-stu-id="28d65-199">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
