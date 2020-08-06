---
title: Применение фильтров к данным тестирования модели | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input row filtering [SQL Server]
- filtering input rows [Analysis Services]
- Mining Accuracy Chart [Analysis Services], filtering input rows
ms.assetid: 9ccc9a23-5597-4b35-a05f-2fc8eb885147
author: minewiskan
ms.author: owend
ms.openlocfilehash: d1fd2b643ae4f7d831cab980ca45b7d43d8b58f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655445"
---
# <a name="apply-filters-to-model-testing-data"></a><span data-ttu-id="472bb-102">Применение фильтров к данным проверки модели</span><span class="sxs-lookup"><span data-stu-id="472bb-102">Apply Filters to Model Testing Data</span></span>
  <span data-ttu-id="472bb-103">Задавая внешний источник данных для использования при тестировании модели, можно при необходимости применить фильтр для ограничения входных данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-103">When you specify an external data source to use in testing a model, you can optionally apply a filter to restrict the input data.</span></span> <span data-ttu-id="472bb-104">Например, необходимо проверить модель конкретно по прогнозам для клиентов с определенным уровнем дохода.</span><span class="sxs-lookup"><span data-stu-id="472bb-104">For example, you might want to test the model specifically for predictions on customers in a certain income range.</span></span>  
  
 <span data-ttu-id="472bb-105">Например, в сценарии целевой рассылки AdventureWorks можно создать выражение фильтра, такое как следующее в ProspectiveBuyer, которое представляет собой таблицу, содержащую проверочные данные, и ограничить проверочные варианты по диапазону доходов:</span><span class="sxs-lookup"><span data-stu-id="472bb-105">For example, in the AdventureWorks targeted mailing scenario, you can create a filter expression like the following one on ProspectiveBuyer, which is the table that contains the testing data, and restrict testing cases by income range:</span></span>  
  
 `[YearlyIncome] = '50000'`  
  
 <span data-ttu-id="472bb-106">Поведение фильтров несколько отличается в зависимости от того, фильтруются обучающие данные модели или набор проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-106">The behavior of filters is slightly different, depending on whether you are filtering model training data or a testing data set:</span></span>  
  
-   <span data-ttu-id="472bb-107">При создании фильтра по набору проверочных данных создается предложение WHERE для входящих данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-107">When you define a filter on a testing data set, you create a WHERE clause on the incoming data.</span></span> <span data-ttu-id="472bb-108">Если фильтруется набор входных данных, используемый для оценки модели, то критерий фильтра преобразуется в инструкцию Transact-SQL и применяется к входной таблице во время создания диаграммы.</span><span class="sxs-lookup"><span data-stu-id="472bb-108">If you are filtering an input data set used for evaluating a model, the filter expression is translated to a Transact-SQL statement and applied to the input table when the chart is created.</span></span> <span data-ttu-id="472bb-109">В результате количество проверочных вариантов можно значительно сократить.</span><span class="sxs-lookup"><span data-stu-id="472bb-109">As a result, the number of test cases can be greatly reduced.</span></span>  
  
-   <span data-ttu-id="472bb-110">Если к модели интеллектуального анализа данных применяется фильтр, именно критерий фильтра переводится в инструкцию расширений интеллектуального анализа данных и применяется к отдельной модели.</span><span class="sxs-lookup"><span data-stu-id="472bb-110">When you apply a filter to a mining model, the filter expression that you create is translated to a Data Mining Extensions (DMX) statement, and applied to the individual model.</span></span> <span data-ttu-id="472bb-111">Таким образом, когда к модели применяется фильтр, для обучения модели используется только подмножество исходных данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-111">Therefore, when you apply a filter to a model, only a subset of the original data is used to train the model.</span></span> <span data-ttu-id="472bb-112">Это может вызывать ошибки, если фильтр применяется к обучаемой модели с одним набором критериев; модель настраивается на определенный набор данных, а проверяется с другим набором критериев.</span><span class="sxs-lookup"><span data-stu-id="472bb-112">This can cause problems if you filter the training model with one set of criteria, so that the model is tuned to a certain set of data, and then test the model with another set of criteria.</span></span>  
  
-   <span data-ttu-id="472bb-113">Если набор проверочных данных был определен во время создания структуры, то к используемым для обучения вариантам модели относятся только те варианты, которые входят в набор обучающих данных структуры интеллектуального анализа данных **и** удовлетворяют условиям фильтра.</span><span class="sxs-lookup"><span data-stu-id="472bb-113">If you defined a testing data set when you created the structure, the model cases used for training include only those cases that are in the mining structure training set **and** which meet the conditions of the filter.</span></span> <span data-ttu-id="472bb-114">Таким образом, если при проверке модели выбрать параметр **Использовать проверочные варианты модели интеллектуального анализа**, то проверочными будут только варианты, которые входят в набор проверочных данных структуры интеллектуального анализа данных и удовлетворяют условиям фильтра.</span><span class="sxs-lookup"><span data-stu-id="472bb-114">Thus, when you are testing a model and select the option **Use mining model test cases**, the testing cases will include only the cases that are in the mining structure test set and which meet the conditions of the filter.</span></span> <span data-ttu-id="472bb-115">Однако если набор контрольных данных определен не был, то к проверочным вариантам модели относятся все варианты набора данных, удовлетворяющие условиям фильтра</span><span class="sxs-lookup"><span data-stu-id="472bb-115">However, if you did not define a holdout data set, the model cases used for testing include all the cases in the data set that meet the filter conditions</span></span>  
  
-   <span data-ttu-id="472bb-116">Кроме того, условия фильтра, применяемые к модели, действуют также для запросов детализации по вариантам модели.</span><span class="sxs-lookup"><span data-stu-id="472bb-116">Filter conditions that you apply on a model also affect drillthrough queries on the model cases.</span></span>  
  
 <span data-ttu-id="472bb-117">В итоге при проверке нескольких моделей, даже если все они основаны на одной и той же структуре интеллектуального анализа данных, необходимо иметь в виду, что они потенциально могут использовать для обучения и проверки различные подмножества данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-117">In summary, when you test multiple models, even if all the models are based on the same mining structure, you must be aware that the models potentially use different subsets of data for training and testing.</span></span> <span data-ttu-id="472bb-118">Это может иметь следующие последствия для диаграмм точности.</span><span class="sxs-lookup"><span data-stu-id="472bb-118">This can have the following effects on accuracy charts:</span></span>  
  
-   <span data-ttu-id="472bb-119">Общее число вариантов в проверочных наборах может быть разным у разных проверяемых моделей.</span><span class="sxs-lookup"><span data-stu-id="472bb-119">The total number of cases in the testing sets can vary among the models being tested.</span></span>  
  
-   <span data-ttu-id="472bb-120">Процентные показатели для каждой модели могут не совпадать в диаграмме, если в моделях используются различные подмножества обучающих и проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-120">The percentages for each model may not align in the chart, if the models use different subsets of training data or testing data.</span></span>  
  
 <span data-ttu-id="472bb-121">Чтобы определить, содержит ли модель стандартный фильтр, который может влиять на результаты, посмотрите значение свойства **Filter** на панели **Свойства** либо выполните запрос к модели с использованием наборов строк схемы интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-121">To determine whether a model contains a predefined filter that might affect results, you can look for the **Filter** property in the **Property** pane, or you can query the model by using the data mining schema rowsets.</span></span> <span data-ttu-id="472bb-122">Например, следующий запрос возвращает текст фильтра для указанной модели:</span><span class="sxs-lookup"><span data-stu-id="472bb-122">For example, the following query returns the filter text for the specified model:</span></span>  
  
 `SELECT [FILTER] FROM $system.DMSCHEMA_MINING_MODELS WHERE MODEL_NAME = 'name of model'`  
  
> [!WARNING]  
>  <span data-ttu-id="472bb-123">Если нужно удалить фильтр из существующей модели интеллектуального анализа данных или если изменяются критерии фильтра, необходимо выполнить повторную обработку модели.</span><span class="sxs-lookup"><span data-stu-id="472bb-123">If you want to remove the filter from an existing mining model, or change the filter conditions, you must reprocess the mining model.</span></span>  
  
 <span data-ttu-id="472bb-124">Дополнительные сведения о видах применяемых фильтров и оценке критериев фильтра см. в разделе [Синтаксис и примеры фильтра модели (службы Analysis Services — интеллектуальный анализ данных)](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="472bb-124">For more information about the kinds of filters you can apply, and how filter expressions are evaluated, see [Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span></span>  
  
### <a name="create-a-filter-on-external-testing-data"></a><span data-ttu-id="472bb-125">Создание фильтра для внешних проверочных данных</span><span class="sxs-lookup"><span data-stu-id="472bb-125">Create a filter on external testing data</span></span>  
  
1.  <span data-ttu-id="472bb-126">Чтобы открыть конструктор интеллектуального анализа данных, дважды щелкните структуру интеллектуального анализа данных, которая содержит модель для проверки.</span><span class="sxs-lookup"><span data-stu-id="472bb-126">Double-click the mining structure that contains the model you want to test, to open Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="472bb-127">Перейдите на вкладку **Диаграмма точности интеллектуального анализа** , а затем на вкладку **Выбор входных данных** .</span><span class="sxs-lookup"><span data-stu-id="472bb-127">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="472bb-128">На вкладке **Выбор входа** в области **Выбор набора данных для диаграммы точности**выберите параметр **Задать другой набор данных**.</span><span class="sxs-lookup"><span data-stu-id="472bb-128">On the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="472bb-129">Нажмите кнопку обзора **(...)** , чтобы открыть диалоговое окно и выбрать внешний набор данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-129">Click the browse button **(...)** to open a dialog box and choose the external data set.</span></span>  
  
5.  <span data-ttu-id="472bb-130">Выберите таблицу вариантов, затем при необходимости добавьте вложенную таблицу.</span><span class="sxs-lookup"><span data-stu-id="472bb-130">Choose the case table, and add a nested table if necessary.</span></span> <span data-ttu-id="472bb-131">Сопоставьте требуемым образом столбцы в модели со столбцами во внешнем источнике данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-131">Map columns in the model to columns in the external data set as necessary.</span></span> <span data-ttu-id="472bb-132">Выберите диалоговое окно **Указание сопоставления столбцов** , чтобы сохранить определение исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="472bb-132">Close the **Specify Column Mapping** dialog box to save the source table definition.</span></span>  
  
6.  <span data-ttu-id="472bb-133">Нажмите кнопку **Открыть редактор фильтров** , чтобы определить фильтр для набора данных.</span><span class="sxs-lookup"><span data-stu-id="472bb-133">Click **Open Filter Editor** to define a filter for the data set.</span></span>  
  
     <span data-ttu-id="472bb-134">Откроется диалоговое окно **Фильтр набора данных** .</span><span class="sxs-lookup"><span data-stu-id="472bb-134">The **Data Set Filter** dialog box opens.</span></span> <span data-ttu-id="472bb-135">Если в структуре содержится вложенная таблица, можно создать фильтр из двух частей.</span><span class="sxs-lookup"><span data-stu-id="472bb-135">If the structure contains a nested table, you can create a filter in two parts.</span></span> <span data-ttu-id="472bb-136">Сначала следует задать условия для таблицы вариантов с помощью диалогового окна **Фильтр набора данных** , затем следует задать условия для вложенных строк с помощью диалогового окна **Фильтр** .</span><span class="sxs-lookup"><span data-stu-id="472bb-136">First, set conditions on the case table by using the **Data Set Filter** dialog box, and then set conditions on the nested rows by using the **Filter** dialog box.</span></span>  
  
7.  <span data-ttu-id="472bb-137">В диалоговом окне **Фильтр набора данных** щелкните верхнюю строку сетки в поле **Столбец структуры интеллектуального анализа данных**, затем выберите таблицу или столбец из списка.</span><span class="sxs-lookup"><span data-stu-id="472bb-137">In the **Data Set Filter** dialog box, click the top row in the grid, under **Mining Structure Column**, and select a table or column from the list.</span></span>  
  
     <span data-ttu-id="472bb-138">Если в представлении источника данных содержатся несколько таблиц или вложенная таблица, сначала следует выбрать имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="472bb-138">If the data source view contains multiple tables, or a nested table, you must first select the table name.</span></span> <span data-ttu-id="472bb-139">В противном случае можно выбирать столбцы из таблицы вариантов напрямую.</span><span class="sxs-lookup"><span data-stu-id="472bb-139">Otherwise, you can select columns from the case table directly.</span></span>  
  
     <span data-ttu-id="472bb-140">Добавьте новую строку в каждый столбец, который необходимо фильтровать.</span><span class="sxs-lookup"><span data-stu-id="472bb-140">Add a new row for each column that you want to filter.</span></span>  
  
8.  <span data-ttu-id="472bb-141">Используйте столбцы **Оператор**и **Значение** , чтобы определить метод фильтрации столбцов.</span><span class="sxs-lookup"><span data-stu-id="472bb-141">Use **Operator**, and **Value** columns to define how the column is filtered.</span></span>  
  
     <span data-ttu-id="472bb-142">**ПРИМЕЧАНИЕ.** Значения следует вводить без кавычек.</span><span class="sxs-lookup"><span data-stu-id="472bb-142">**Note** Type values without using quotation marks.</span></span>  
  
9. <span data-ttu-id="472bb-143">Щелкните текстовое поле **И/ИЛИ** и выберите логический оператор, чтобы определить метод сочетания нескольких условий.</span><span class="sxs-lookup"><span data-stu-id="472bb-143">Click the **And/Or** text box and select a logical operator to define how multiple conditions are combine.</span></span>  
  
10. <span data-ttu-id="472bb-144">При необходимости нажмите кнопку обзора **(...)** справа от текстового поля **значение** , чтобы открыть диалоговое окно **Фильтр** и задать условия для вложенной таблицы или отдельных столбцов таблицы вариантов.</span><span class="sxs-lookup"><span data-stu-id="472bb-144">Optionally, click the browse button **(...)** at the right of the **Value** text box to open the **Filter** dialog box and set conditions on the nested table or on the individual case table columns.</span></span>  
  
11. <span data-ttu-id="472bb-145">Проверьте правильность условий завершенного фильтра, просмотрев текст на панели **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="472bb-145">Verify that the completed filter conditions are correct by viewing the text in the **Expression** pane.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="472bb-146">Условие фильтра применяется к источнику данных при создании диаграммы точности.</span><span class="sxs-lookup"><span data-stu-id="472bb-146">The filter condition is applied to the data source when you create the accuracy chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472bb-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="472bb-147">See Also</span></span>  
 <span data-ttu-id="472bb-148">[Выбор и сопоставьте данные тестирования модели](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="472bb-148">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 <span data-ttu-id="472bb-149">[Использование данных вложенной таблицы в качестве входных для диаграммы точности](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span><span class="sxs-lookup"><span data-stu-id="472bb-149">[Using Nested Table Data as an Input for an Accuracy Chart](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span></span>  
 [<span data-ttu-id="472bb-150">Выбор типа диаграммы точности и задание параметров диаграммы</span><span class="sxs-lookup"><span data-stu-id="472bb-150">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
