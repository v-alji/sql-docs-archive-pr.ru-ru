---
title: Выбор и отображение входных данных для прогнозирующего запроса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- tables [Analysis Services], prediction queries
- Mining Model Prediction [Analysis Services], input tables
ms.assetid: 00d330a0-879d-4da0-9f29-53c288116f4d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54e11752d6278e01e50a379bf7bb57521ff9bb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658563"
---
# <a name="choose-and-map-input-data-for-a-prediction-query"></a><span data-ttu-id="cdbd3-102">Выбор и сопоставление входных данных для прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="cdbd3-102">Choose and Map Input Data for a Prediction Query</span></span>
  <span data-ttu-id="cdbd3-103">Создание прогнозов на основе модели интеллектуального анализа данных обычно производится посредством передачи в модель новых данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-103">When you create predictions from a mining model, you generally do this by feeding new data into the model.</span></span> <span data-ttu-id="cdbd3-104">(Исключение составляют модели временных рядов, в которых прогнозы могут создаваться только на основании исторических данных.) Для передачи в модель новых данных убедитесь, что данные доступны в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-104">(The exception is time series models, which can make predictions based on historical data only.) To provide the model with new data, you must make sure that the data is available as part of a data source view.</span></span> <span data-ttu-id="cdbd3-105">Если заранее известно, какие данные будут использоваться для прогноза, их можно включить в представление источника данных, который использовался для создания модели.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-105">If you know in advance which data you will use for prediction, you can include it in the data source view that you used to create the model.</span></span> <span data-ttu-id="cdbd3-106">В противном случае может понадобиться создать новое представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-106">Otherwise, you might have to create a new data source view.</span></span> <span data-ttu-id="cdbd3-107">Дополнительные сведения см. в разделе [Представления источников данных в многомерных моделях](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="cdbd3-107">For more information, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="cdbd3-108">Иногда необходимые данные могут содержаться в более чем одной таблице в соединении «один ко многим».</span><span class="sxs-lookup"><span data-stu-id="cdbd3-108">Sometimes the data that you need might be contained within more than one table in a one-to-many join.</span></span> <span data-ttu-id="cdbd3-109">Это происходит при использовании данных для моделей взаимосвязей или моделей кластеризации последовательностей, использующих таблицу вариантов, связанную со вложенной таблицей, которая содержит подробные сведения о продуктах или транзакциях.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-109">This is the case with data used for association models or sequence clustering models, which use a case table linked to a nested table that contains product or transaction details.</span></span> <span data-ttu-id="cdbd3-110">Если в вашей модели используется структура с таблицей вариантов и вложенной таблицей, то в данных, которые используются для прогнозирования, также должна использоваться структура с таблицей вариантов и вложенной таблицей.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-110">If your model uses a case-nested table structure, the data that you use for prediction must also have a case-nested table structure.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="cdbd3-111">Добавлять новые столбцы или сопоставлять столбцы из другого представления источников данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-111">You cannot add new columns or map columns that are in a different data source view.</span></span> <span data-ttu-id="cdbd3-112">Выбранное представление источника данных должно содержать все столбцы, необходимые для прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-112">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
 <span data-ttu-id="cdbd3-113">После того как вы определили список таблиц, содержащих данные для использования в прогнозах, будет необходимо сопоставить столбцы внешних данных со столбцами в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-113">After you have identified the tables that contain the data you will use for predictions, you must map the columns in the external data to the columns in the mining model.</span></span> <span data-ttu-id="cdbd3-114">Например, если ваша модель прогнозирует поведение покупателей на основании демографических данных и ответов, полученных в ходе опросов, то входные данные должны содержать информацию, в целом соответствующую содержимому модели.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-114">For example, if your model predicts customer purchasing behavior based on demographics and survey responses, your input data should contains information that generally corresponds to what is in the model.</span></span> <span data-ttu-id="cdbd3-115">Сопоставлять данные для каждого из столбцов не требуется, но чем больше столбцов будет сопоставлено, тем выше качество прогноза.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-115">You do not need to have matching data for every single column, but the more columns you can match, the better.</span></span> <span data-ttu-id="cdbd3-116">При попытке сопоставления столбцов с различными типами данных может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-116">If you try to map columns that have different data types, you might get an error.</span></span> <span data-ttu-id="cdbd3-117">В этом случае вы можете определить именованное вычисление в представлении источника данных, чтобы привести или преобразовать тип данных нового столбца к типу, требуемому в модели.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-117">In that case, you could define a named calculation in the data source view to cast or convert the new column data to the data type required by the model.</span></span> <span data-ttu-id="cdbd3-118">Дополнительные сведения см. [в разделе Определение именованных вычислений в представлении источника данных &#40;Analysis Services&#41;](../multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="cdbd3-118">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md).</span></span>  
  
 <span data-ttu-id="cdbd3-119">При выборе используемых для прогноза данных некоторые столбцы из выбранного источника данных могут автоматически сопоставляться со столбцами модели интеллектуального анализа данных на основе сходства имен и совпадения типов данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-119">When you choose the data to use for prediction, some columns in the selected data source might be automatically mapped to the mining model columns, based on name similarity and matching data type.</span></span> <span data-ttu-id="cdbd3-120">Диалоговое окно **Изменение сопоставления** на вкладке **Прогнозирование моделей интеллектуального анализа данных** можно использовать для изменения существующих сопоставлений столбцов, удаления неверных сопоставлений и создания новых сопоставлений существующих столбцов.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-120">You can use the **Modify Mapping** dialog box in the **Mining Model Prediction** to change the columns that are mapped, delete inappropriate mappings, or create new mappings for existing columns.</span></span> <span data-ttu-id="cdbd3-121">Область конструктора **Модель интеллектуального анализа данных** также поддерживает изменение соединений посредством перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-121">The **Mining Model Prediction** design surface also supports drag-and-drop editing of connections.</span></span>  
  
-   <span data-ttu-id="cdbd3-122">Чтобы создать новое соединение, просто выберите столбец в таблице **Модель интеллектуального анализа данных** и перетащите его в соответствующий столбец в таблице **Выбор входных таблиц** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-122">To create a new connection, just select a column in the **Mining Model** table and drag it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
-   <span data-ttu-id="cdbd3-123">Для удаления соединения выделите линию соединения и нажмите клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-123">To remove a connection, select the connection line and press the DELETE key.</span></span>  
  
 <span data-ttu-id="cdbd3-124">В следующей процедуре описывается изменение соединений, созданных между таблицей вариантов и вложенной таблицей, используемой в качестве входных данных для прогнозирующего запроса в диалоговом окне **Определение вложенного соединения** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-124">The following procedure describes how you can modify the joins that have been created between the case table and a nested table used as inputs to a prediction query, using the **Specify Nested Join** dialog box.</span></span>  
  
### <a name="select-an-input-table"></a><span data-ttu-id="cdbd3-125">Выбор входной таблицы</span><span class="sxs-lookup"><span data-stu-id="cdbd3-125">Select an input table</span></span>  
  
1.  <span data-ttu-id="cdbd3-126">В таблице **Выбор входных таблиц** на вкладке **Диаграмма точности интеллектуального анализа** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]нажмите **Выбор таблицы вариантов**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-126">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="cdbd3-127">Откроется диалоговое окно **Выбор таблицы** , в котором можно указать таблицу, содержащую данные, на которых будут основаны запросы.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-127">The **Select Table** dialog box opens, in which you can select the table that contains the data on which to base your queries.</span></span>  
  
2.  <span data-ttu-id="cdbd3-128">В диалоговом окне **Выбор таблицы** выберите источник данных из списка **Источник данных** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-128">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span>  
  
3.  <span data-ttu-id="cdbd3-129">В поле **Имя таблицы/представления**выберите таблицу, содержащую данные, с помощью которых будут проверяться модели.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-129">Under **Table/View Name**, select the table that contains the data you want to use to test the models.</span></span>  
  
4.  <span data-ttu-id="cdbd3-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-130">Click **OK**.</span></span>  
  
     <span data-ttu-id="cdbd3-131">Столбцы в структуре интеллектуального анализа данных автоматически сопоставляются со столбцами, имеющими то же имя во входной таблице.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-131">The columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
### <a name="change-the-way-that-input-data-is-mapped-to-the-model"></a><span data-ttu-id="cdbd3-132">Изменение способа сопоставления входных данных с моделью</span><span class="sxs-lookup"><span data-stu-id="cdbd3-132">Change the way that input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="cdbd3-133">В конструкторе интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]перейдите на вкладку **Прогнозирование моделей интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-133">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="cdbd3-134">В меню **Модель интеллектуального анализа данных** выберите пункт **Изменить подключения**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-134">On the **Mining Model** menu, select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="cdbd3-135">Откроется диалоговое окно **Изменение сопоставления** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-135">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="cdbd3-136">Столбец в этом диалоговом окне, **Столбец модели интеллектуального анализа данных** , содержит список столбцов выбранной структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-136">In this dialog box, the column **Mining Model Column** lists the columns in the selected mining structure.</span></span> <span data-ttu-id="cdbd3-137">В столбце **Столбец таблицы** перечисляются столбцы внешнего источника данных, выбранные в диалоговом окне **Выбор входных таблиц** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-137">The column **Table Column** lists the columns in the external data source that you chose in the **SelectInput Table(s)** dialog box.</span></span> <span data-ttu-id="cdbd3-138">Столбцы внешнего источника данных сопоставляются столбцам модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-138">The columns in the external data source are mapped to columns in the mining model.</span></span>  
  
3.  <span data-ttu-id="cdbd3-139">В списке **Столбцы таблицы**выберите строку, соответствующую столбцу модели интеллектуального анализа данных, сопоставление с которым нужно задать.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-139">Under **Table Column**, select the row that corresponds to the mining model column that you want to map to.</span></span>  
  
4.  <span data-ttu-id="cdbd3-140">Выберите столбец из списка доступных столбцов внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-140">Select a new column from the list of available columns in the external data source.</span></span> <span data-ttu-id="cdbd3-141">Выберите пустой элемент в списке, чтобы удалить сопоставление столбца.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-141">Select the blank item in the list to delete the column mapping.</span></span>  
  
5.  <span data-ttu-id="cdbd3-142">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="cdbd3-143">Новые сопоставления столбцов отображаются в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-143">The new column mappings are displayed in the designer.</span></span>  
  
### <a name="remove-a-relationship-between-input-tables"></a><span data-ttu-id="cdbd3-144">Удаление связи между входными таблицами</span><span class="sxs-lookup"><span data-stu-id="cdbd3-144">Remove a relationship between input tables</span></span>  
  
1.  <span data-ttu-id="cdbd3-145">В таблице **Выбор входных таблиц** на вкладке **Прогнозирование моделей интеллектуального анализа данных** в конструкторе интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]нажмите кнопку **Изменить соединение**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-145">On the **Select Input Table(s)** table of the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Modify Join**.</span></span>  
  
     <span data-ttu-id="cdbd3-146">Откроется диалоговое окно **Указание вложенного соединения** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-146">The **Specify Nested Join** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="cdbd3-147">Выберите связь.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-147">Select a relationship.</span></span>  
  
3.  <span data-ttu-id="cdbd3-148">Нажмите кнопку **Удалить связь**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-148">Click **Remove Relationship**.</span></span>  
  
4.  <span data-ttu-id="cdbd3-149">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-149">Click **OK**.</span></span>  
  
     <span data-ttu-id="cdbd3-150">Связь между таблицей вариантов и вложенной таблицей удалится.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-150">The relationship between the case table and the nested table has been removed.</span></span>  
  
### <a name="create-a-new-relationship-between-input-tables"></a><span data-ttu-id="cdbd3-151">Создание новой связи между входными таблицами</span><span class="sxs-lookup"><span data-stu-id="cdbd3-151">Create a new relationship between input tables</span></span>  
  
1.  <span data-ttu-id="cdbd3-152">В таблице **Выбор входных таблиц** на вкладке **Модель интеллектуального анализа данных** в конструкторе интеллектуального анализа данных нажмите кнопку **Изменить соединение**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-152">On the **Select Input Table(s)** table of the **Mining Model Prediction** tab in Data Mining Designer, click **Modify Join**.</span></span>  
  
     <span data-ttu-id="cdbd3-153">Откроется диалоговое окно **Указание вложенного соединения** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-153">The **Specify Nested Join** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="cdbd3-154">Нажмите кнопку **Создать связь**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-154">Click **Add Relationship**.</span></span>  
  
     <span data-ttu-id="cdbd3-155">Открывается диалоговое окно **Создание связи** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-155">The **Create Relationship** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="cdbd3-156">Выберите ключ вложенной таблицы в списке **Исходные столбцы**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-156">Select the key of the nested table in **Source Columns**.</span></span>  
  
4.  <span data-ttu-id="cdbd3-157">Выберите ключ таблицы вариантов в списке **Целевые столбцы**.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-157">Select the key of the case table in **Destination Columns**.</span></span>  
  
5.  <span data-ttu-id="cdbd3-158">Нажмите кнопку **ОК** в диалоговом окне **Создание связи** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-158">Click **OK** in the **Create Relationship** dialog box.</span></span>  
  
6.  <span data-ttu-id="cdbd3-159">Нажмите кнопку **ОК** в диалоговом окне **Указание вложенного соединения** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-159">Click **OK** in the **Specify Nested Join** dialog box.</span></span>  
  
     <span data-ttu-id="cdbd3-160">Между таблицей вариантов и вложенной таблицей создастся новая связь.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-160">A new relationship has been created between the case table and the nested table.</span></span>  
  
### <a name="add-a-nested-table-to-the-input-tables-of-a-prediction-query"></a><span data-ttu-id="cdbd3-161">Добавление вложенной таблицы во входные таблицы прогнозирующего запроса</span><span class="sxs-lookup"><span data-stu-id="cdbd3-161">Add a nested table to the input tables of a prediction query</span></span>  
  
1.  <span data-ttu-id="cdbd3-162">На вкладке **Прогноз модели интеллектуального анализа данных** конструктора интеллектуального анализа данных нажмите кнопку **Выбрать таблицу вариантов** , чтобы открыть диалоговое окно **Выбор таблицы** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-162">On the **Mining Model Prediction** tab in Data Mining Designer, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cdbd3-163">Вложенную таблицу невозможно добавить ко входам, пока не задана таблица вариантов.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-163">You cannot add a nested table to the inputs unless you have specified a case table.</span></span> <span data-ttu-id="cdbd3-164">При использовании вложенной таблицы в модели интеллектуального анализа данных также обязательно должна использоваться вложенная таблица.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-164">Use of a nested table requires that the mining model you are using for prediction also uses a nested table.</span></span>  
  
2.  <span data-ttu-id="cdbd3-165">В диалоговом окне **Выбор таблицы** выберите источник данных из списка **Источник данных** и в представлении источника данных выберите таблицу, в которой содержатся данные варианта.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-165">In the **Select Table** dialog box, select a data source from the **Data Source** list, and select the table in the data source view that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="cdbd3-166">Нажмите кнопку **Выбрать вложенную таблицу** , чтобы открыть диалоговое окно **Выбор таблицы** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-166">Click **Select Nested Table** to open the **Select Table** dialog box.</span></span>  
  
4.  <span data-ttu-id="cdbd3-167">В диалоговом окне **Выбор таблицы** выберите источник данных из списка **Источник данных** и в представлении источника данных выберите таблицу, в которой содержатся вложенные данные.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-167">In the **Select Table** dialog box, select a data source from the **Data Source** list, and select the table in the data source view that contains the nested data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="cdbd3-168">Если связь уже имеется, то столбцы в модели интеллектуального анализа данных автоматически сопоставляются со столбцами, имеющими то же имя во входной таблице.</span><span class="sxs-lookup"><span data-stu-id="cdbd3-168">If a relationship already exists, the columns in the mining model are automatically mapped to the columns that have the same name in the input table.</span></span> <span data-ttu-id="cdbd3-169">Связь между вложенной таблицей и таблицей вариантов можно изменить, нажав кнопку **Изменить соединение**, после чего откроется диалоговое окно **Создание связи** .</span><span class="sxs-lookup"><span data-stu-id="cdbd3-169">You can modify the relationship between the nested table and the case table by clicking **Modify Join**, which opens the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdbd3-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="cdbd3-170">See Also</span></span>  
 [<span data-ttu-id="cdbd3-171">Прогнозирующие запросы (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="cdbd3-171">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
